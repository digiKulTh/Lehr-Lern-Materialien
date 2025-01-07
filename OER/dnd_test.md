<!--
author:   Your Name
email:    your@email.com
version:  0.1.0
language: en
narrator: US English Female

script:   https://cdnjs.cloudflare.com/ajax/libs/Sortable/1.14.0/Sortable.min.js

@dragdroporder
<div style="width: 100%; max-width: 600px; padding: 20px; border: 1px solid #ccc; border-radius: 8px;">
  <div class="choices-container" style="display: flex; flex-direction: column; gap: 10px;" id="quiz-@0">
    @1
  </div>
  <div class="feedback" style="margin-top: 20px; font-weight: bold; text-align: center;"></div>
</div>

<script>
  void setTimeout(() => {
    (function(){
        const quizId = '@0';
        const container = document.querySelector(`#quiz-${quizId}`);

        const feedback = container.nextElementSibling;
        feedback.textContent = "🤔";
        feedback.style.fontSize = "2em";
        const correctAnswers = '@2'.split(';');
        
        new Sortable(container, {
          animation: 150,
          onEnd: function() {
            const choices = Array.from(container.querySelectorAll('.choice'));
            const currentOrder = choices.map(choice => choice.textContent.trim());
            
            const isCorrect = currentOrder.length === correctAnswers.length && 
                             currentOrder.every((answer, index) => answer === correctAnswers[index]);
            
            if (isCorrect) {
              feedback.textContent = "✅";
              feedback.style.fontSize = "2em";
            } else {
              feedback.textContent = "❌";
              feedback.style.fontSize = "2em";
            }
          }
        });
        
        container.querySelectorAll('.choice').forEach(element => {
          element.setAttribute('style', 'padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move; user-select: none;');
        });
    })();
  }, 100);
</script>
@end

@dragdropmultiple
<div style="width: 100%; max-width: 600px; padding: 20px; border: 1px solid #ccc; border-radius: 8px;" id="quiz-@0">
  <div style="display: flex; gap: 20px;">
    <div style="flex: 1;">
      <div style="font-weight: bold; margin-bottom: 10px;">Pool:</div>
      <div class="pool-container" style="min-height: 50px; padding: 10px; background-color: #f8f8f8; border: 1px dashed #ccc; border-radius: 4px; display: flex; flex-direction: column; gap: 10px;" id="pool-@0">
        @1
      </div>
    </div>
    <div style="flex: 1;">
      <div style="font-weight: bold; margin-bottom: 10px;">Your Selection:</div>
      <div class="target-container" style="min-height: 50px; padding: 10px; background-color: #f8f8f8; border: 1px dashed #ccc; border-radius: 4px; display: flex; flex-direction: column; gap: 10px;" id="target-@0">
      </div>
    </div>
  </div>
  
  <div class="feedback" style="margin-top: 20px; font-weight: bold; text-align: center;"></div>
</div>

<script>
  void setTimeout(() => {
    (function(){
        const quizId = '@0';
        const quizContainer = document.querySelector(`#quiz-${quizId}`);

        const poolContainer = quizContainer.querySelector('.pool-container');
        const targetContainer = quizContainer.querySelector('.target-container');
        const feedback = quizContainer.querySelector('.feedback');
        feedback.textContent = "🤔";
        feedback.style.fontSize = "2em";
        const correctAnswers = new Set('@2'.split(';'));
        
        poolContainer.querySelectorAll('.choice').forEach(element => {
          element.setAttribute('style', 'padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move; user-select: none;');
        });

        new Sortable(poolContainer, {
          group: {
            name: quizId,
            put: true
          },
          animation: 150,
          onEnd: checkAnswer
        });
        
        new Sortable(targetContainer, {
          group: {
            name: quizId,
            pull: true,
            put: true
          },
          animation: 150,
          onAdd: checkAnswer,
          onRemove: checkAnswer
        });

        function checkAnswer() {
          const currentAnswers = new Set(
            Array.from(targetContainer.querySelectorAll('.choice'))
              .map(choice => choice.textContent.trim())
          );

          const isCorrect = currentAnswers.size === correctAnswers.size &&
                           [...currentAnswers].every(answer => correctAnswers.has(answer));
          
          if (isCorrect) {
            feedback.textContent = "✅";
            feedback.style.fontSize = "2em";
          } else {
            feedback.textContent = "❌";
            feedback.style.fontSize = "2em";
          }
        }
    })();
  }, 100);
</script>
@end
-->

# Drag and Drop Quizzes

**Drag and drop in order**

Try to order these items correctly by dragging and dropping them!

@dragdroporder(@uid,
<div class="choice">4</div>
<div class="choice">2</div>
<div class="choice">3</div>
<div class="choice">1</div>,1;2;3;4)

Try to order these items correctly by dragging and dropping them (hint: reverse order)!

@dragdroporder(@uid,
<div class="choice">4</div>
<div class="choice">2</div>
<div class="choice">1</div>
<div class="choice">3</div>,4;3;2;1)

**Drag and drop multiple choice**

Select the correct numbers from the pool (hint: odd numbers only)!

@dragdropmultiple(@uid,
<div class="choice">1</div>
<div class="choice">2</div>
<div class="choice">3</div>
<div class="choice">4</div>
<div class="choice">5</div>
<div class="choice">6</div>,1;3;5)

Select the correct numbers from the pool (hint: even numbers only)!

@dragdropmultiple(@uid,
<div class="choice">1</div>
<div class="choice">2</div>
<div class="choice">3</div>
<div class="choice">4</div>
<div class="choice">5</div>
<div class="choice">6</div>,2;4;6)
