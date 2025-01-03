<!--
author:   Your Name
email:    your@email.com
version:  0.1.0
language: en
narrator: US English Female

script: https://cdnjs.cloudflare.com/ajax/libs/Sortable/1.14.0/Sortable.min.js

@DragDropQuiz
<div class="quiz-container">
  <div class="question">@0</div>
  <div class="choices-container">
    @1
  </div>
  <div class="feedback"></div>
</div>

<script>
  // Initialize Sortable
  new Sortable(document.querySelector('.choices-container'), {
    animation: 150,
    onEnd: function() {
      checkAnswer();
    }
  });

  function checkAnswer() {
    const choices = Array.from(document.querySelectorAll('.choice'));
    const userAnswer = choices.map(choice => choice.textContent.trim());
    const correctAnswer = [@2].map(String);
    
    const feedback = document.querySelector('.feedback');
    
    if (arraysEqual(userAnswer, correctAnswer)) {
      feedback.textContent = "Correct!";
      feedback.style.color = "green";
    } else {
      feedback.textContent = "Try again!";
      feedback.style.color = "red";
    }
  }
  
  function arraysEqual(a, b) {
    return JSON.stringify(a) === JSON.stringify(b);
  }
</script>

<style>
.quiz-container {
  max-width: 600px;
  margin: 20px auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
}

.question {
  font-size: 18px;
  margin-bottom: 20px;
}

.choices-container {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.choice {
  padding: 10px;
  background-color: #f0f0f0;
  border: 1px solid #ddd;
  border-radius: 4px;
  cursor: move;
  user-select: none;
  transition: background-color 0.2s;
}

.choice:hover {
  background-color: #e0e0e0;
}

.feedback {
  margin-top: 20px;
  font-weight: bold;
  text-align: center;
}

@media (max-width: 480px) {
  .quiz-container {
    margin: 10px;
    padding: 15px;
  }
  
  .question {
    font-size: 16px;
  }
  
  .choice {
    padding: 8px;
  }
}
</style>
@end
-->

What is the correct order of these numbers?

@DragDropQuiz(Put these numbers in ascending order:,
<div class="choice">4</div>
<div class="choice">2</div>
<div class="choice">3</div>
<div class="choice">1</div>,
1,2,3,4)
