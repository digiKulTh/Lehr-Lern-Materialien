<!--
author:   Your Name
email:    your@email.com
version:  0.1.0
language: en
narrator: US English Female

script:   https://cdnjs.cloudflare.com/ajax/libs/Sortable/1.14.0/Sortable.min.js

@dragdroporder: @0
<div style="width: 100%; max-width: 600px; padding: 20px; border: 1px solid #ccc; border-radius: 8px;">
  <div class="question" style="font-size: 18px; margin-bottom: 20px;">Order these items:</div>
  <div class="choices-container" style="display: flex; flex-direction: column; gap: 10px;" id="quiz-@uid">
    @1
  </div>
  <div class="feedback" style="margin-top: 20px; font-weight: bold; text-align: center;"></div>
</div>

<script>
  (function(){
    const quizId = "@uid";
    const container = document.querySelector(`#quiz-${quizId}`);
    const feedback = container.nextElementSibling;
    const correctAnswers = "@2".split(';');
    
    new Sortable(container, {
      animation: 150,
      onEnd: function() {
        const choices = Array.from(container.querySelectorAll('.choice'));
        const currentOrder = choices.map(choice => choice.textContent.trim());
        
        const isCorrect = currentOrder.length === correctAnswers.length && 
                         currentOrder.every((answer, index) => answer === correctAnswers[index]);
        
        if (isCorrect) {
          feedback.textContent = "Correct!";
          feedback.style.color = "green";
        } else {
          feedback.textContent = "Try again!";
          feedback.style.color = "red";
        }
      }
    });
  })();
</script>
@end

@dragdropmultiple: @0
<div style="width: 100%; max-width: 600px; padding: 20px; border: 1px solid #ccc; border-radius: 8px;" id="quiz-@uid">
  <div class="question" style="font-size: 18px; margin-bottom: 20px;">Select the correct items:</div>
  
  <div style="display: flex; gap: 20px;">
    <div style="flex: 1;">
      <div style="font-weight: bold; margin-bottom: 10px;">Pool:</div>
      <div class="pool-container" style="min-height: 50px; padding: 10px; background-color: #f8f8f8; border: 1px dashed #ccc; border-radius: 4px;">
        @1
      </div>
    </div>
    
    <div style="flex: 1;">
      <div style="font-weight: bold; margin-bottom: 10px;">Your Selection:</div>
      <div class="target-container" style="min-height: 50px; padding: 10px; background-color: #f8f8f8; border: 1px dashed #ccc; border-radius: 4px;">
      </div>
    </div>
  </div>
  
  <div class="feedback" style="margin-top: 20px; font-weight: bold; text-align: center;"></div>
</div>

<script>
  (function(){
    const quizId = "@uid";
    const quizContainer = document.querySelector(`#quiz-${quizId}`);
    const poolContainer = quizContainer.querySelector('.pool-container');
    const targetContainer = quizContainer.querySelector('.target-container');
    const feedback = quizContainer.querySelector('.feedback');
    const correctAnswers = new Set("@2".split(';'));
    
    new Sortable(poolContainer, {
      group: quizId,
      animation: 150
    });
    
    new Sortable(targetContainer, {
      group: quizId,
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
        feedback.textContent = "Correct!";
        feedback.style.color = "green";
      } else {
        feedback.textContent = "Try again!";
        feedback.style.color = "red";
      }
    }
  })();
</script>
@end
-->

# Drag and Drop Quizzes

**Order the numbers**

@dragdroporder(Order these numbers from smallest to largest,
<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move;">4</div>
<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move;">2</div>
<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move;">3</div>
<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move;">1</div>,1;2;3;4)

**Select the odd numbers**

@dragdropmultiple(Select all odd numbers,
<div class="choice" style="padding: 10px; background-color: #fff; border: 1px solid #ddd; border-radius: 4px; cursor: move;">1</div>
<div class="choice" style="padding: 10px; background-color: #fff; border: 1px solid #ddd; border-radius: 4px; cursor: move;">2</div>
<div class="choice" style="padding: 10px; background-color: #fff; border: 1px solid #ddd; border-radius: 4px; cursor: move;">3</div>
<div class="choice" style="padding: 10px; background-color: #fff; border: 1px solid #ddd; border-radius: 4px; cursor: move;">4</div>
<div class="choice" style="padding: 10px; background-color: #fff; border: 1px solid #ddd; border-radius: 4px; cursor: move;">5</div>
<div class="choice" style="padding: 10px; background-color: #fff; border: 1px solid #ddd; border-radius: 4px; cursor: move;">6</div>,1;3;5)
