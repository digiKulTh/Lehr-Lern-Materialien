<!--
author:   Your Name
email:    your@email.com
version:  0.1.0
language: en
narrator: US English Female

script:   https://cdnjs.cloudflare.com/ajax/libs/Sortable/1.14.0/Sortable.min.js

@dragdrop
<section style="width: 100%; max-width: 600px; margin: 20px auto; padding: 20px; border: 1px solid #ccc; border-radius: 8px;">
  <div class="question" style="font-size: 18px; margin-bottom: 20px;">@0</div>
  <div class="choices-container" style="display: flex; flex-direction: column; gap: 10px;" id="quiz-@0">
    @1
  </div>
  <div class="feedback" style="margin-top: 20px; font-weight: bold; text-align: center;"></div>
</section>

<script>
  (function(){
    const quizId = '@0'.replace(/[^a-zA-Z0-9]/g, '');
    const container = document.querySelector(`#quiz-${quizId}`);
    const feedback = container.nextElementSibling;
    const correctAnswers = '@2'.split(',');
    
    new Sortable(container, {
      animation: 150,
      onEnd: function() {
        const choices = Array.from(container.querySelectorAll('.choice'));
        const currentOrder = choices.map(choice => choice.textContent.trim());
        
        console.log('Current order:', currentOrder);
        console.log('Correct answers:', correctAnswers);
        
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
-->

# Drag and Drop Quiz

Try to order these items correctly by dragging and dropping them!

@dragdrop(quiz1,
<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move; user-select: none;">4</div>
<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move; user-select: none;">2</div>
<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move; user-select: none;">3</div>
<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move; user-select: none;">1</div>,
1,2,3,4)

Try another example:

@dragdrop(quiz2,
<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move; user-select: none;">Watermelon</div>
<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move; user-select: none;">Apple</div>
<div class="choice" style="padding: 10px; background-color: #f0f0f0; border: 1px solid #ddd; border-radius: 4px; cursor: move; user-select: none;">Grape</div>,
Grape,Apple,Watermelon)
