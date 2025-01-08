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
  </div>
  <div class="feedback" style="margin-top: 20px; font-size:2em; font-weight: bold; text-align: center;">🤔</div>
</div>

<script>
  void setTimeout(() => {
    (function(){
        const quizId = '@0';
        const container = document.querySelector(`#quiz-${quizId}`);

        const feedback = container.nextElementSibling;
        const correctAnswers = '@2'.split('|');

        const initialOrder = '@1'.split('|');
        container.innerHTML = initialOrder.map(item => 
          `<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move; user-select: none;">${item}</div>`
        ).join('');
        
        new Sortable(container, {
          animation: 150,
          onEnd: function() {
            const choices = Array.from(container.querySelectorAll('.choice'));
            const currentOrder = choices.map(choice => choice.textContent.trim());
            
            const isCorrect = currentOrder.length === correctAnswers.length && 
                             currentOrder.every((answer, index) => answer === correctAnswers[index]);
            
            if (isCorrect) {
              feedback.textContent = "✅";
            } else {
              feedback.textContent = "❌";
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
      </div>
    </div>
    <div style="flex: 1;">
      <div style="font-weight: bold; margin-bottom: 10px;">Your Selection:</div>
      <div class="target-container" style="min-height: 50px; padding: 10px; background-color: #f8f8f8; border: 1px dashed #ccc; border-radius: 4px; display: flex; flex-direction: column; gap: 10px;" id="target-@0">
      </div>
    </div>
  </div>
  
  <div class="feedback" style="margin-top: 20px; font-size: 2em; font-weight: bold; text-align: center;">🤔</div>
</div>

<script>
  void setTimeout(() => {
    (function(){
        const quizId = '@0';
        const quizContainer = document.querySelector(`#quiz-${quizId}`);

        const poolContainer = quizContainer.querySelector('.pool-container');
        const targetContainer = quizContainer.querySelector('.target-container');
        const feedback = quizContainer.querySelector('.feedback');
        const correctAnswers = new Set('@2'.split('|'));

        const initialOrder = '@1'.split('|');
        poolContainer.innerHTML = initialOrder.map(item => 
          `<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move; user-select: none;">${item}</div>`
        ).join('');

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
          } else {
            feedback.textContent = "❌";
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

@dragdroporder(@uid,4|2|3|1,1|2|3|4)

Try to order these items correctly by dragging and dropping them (hint: reverse order)!

@dragdroporder(@uid,4|2|1|3,4|3|2|1)

**Drag and drop multiple choice**

Select the correct numbers from the pool (hint: odd numbers only)!

@dragdropmultiple(@uid,1|2|3|4|5|6,1|3|5)

Select the correct numbers from the pool (hint: even numbers only)!

@dragdropmultiple(@uid,1|2|3|4|5|6,2|4|6)
