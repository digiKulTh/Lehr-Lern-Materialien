<!--
author:  Your Name
email:   your.email@example.com
version:  0.0.1
language: en
narrator: US English Female

comment:  A simple quiz about LiaScript using drag and drop functionality
-->

# LiaScript Quiz

Fill in the blanks by dragging the correct words to complete the sentences about LiaScript.

<div id="quiz-container">
<div id="word-bank">
  <div class="draggable" draggable="true">Markdown</div>
  <div class="draggable" draggable="true">interactive</div>
  <div class="draggable" draggable="true">educational</div>
  <div class="draggable" draggable="true">quizzes</div>
  <div class="draggable" draggable="true">animations</div>
</div>

<div id="sentences">
  1. LiaScript is based on ________ syntax.
  <div class="droppable" data-answer="Markdown"></div>
  
  2. It is designed specifically for ________ content.
  <div class="droppable" data-answer="educational"></div>
  
  3. The platform allows creation of ________ elements.
  <div class="droppable" data-answer="interactive"></div>
  
  4. Users can create ________ to test knowledge.
  <div class="droppable" data-answer="quizzes"></div>
  
  5. LiaScript supports ________ to make content dynamic.
  <div class="droppable" data-answer="animations"></div>
</div>

<button onclick="checkAnswers()">Check Answers</button>
<div id="result"></div>
</div>

<script>
// Initialize drag & drop functionality
document.addEventListener('DOMContentLoaded', () => {
    const draggables = document.querySelectorAll('.draggable');
    const droppables = document.querySelectorAll('.droppable');

    // Add event listeners to draggable elements
    draggables.forEach(draggable => {
        draggable.addEventListener('dragstart', dragStart);
        draggable.addEventListener('dragend', dragEnd);
    });

    // Add event listeners to droppable elements
    droppables.forEach(droppable => {
        droppable.addEventListener('dragover', dragOver);
        droppable.addEventListener('drop', drop);
    });
});

let draggedElement = null;

function dragStart(e) {
    draggedElement = this;
    setTimeout(() => this.classList.add('dragging'), 0);
}

function dragEnd(e) {
    this.classList.remove('dragging');
}

function dragOver(e) {
    e.preventDefault();
}

function drop(e) {
    e.preventDefault();
    const droppable = e.target;
    
    // If dragged element was already in a droppable, clear that droppable
    if (draggedElement.parentElement.classList.contains('droppable')) {
        draggedElement.parentElement.innerHTML = '';
    }
    
    // Clear target droppable and append dragged element
    droppable.innerHTML = '';
    droppable.appendChild(draggedElement);
    draggedElement.classList.remove('dragging');
}

function checkAnswers() {
    const droppables = document.querySelectorAll('.droppable');
    let correct = 0;
    let total = droppables.length;
    
    droppables.forEach(droppable => {
        if (droppable.children.length > 0) {
            const answer = droppable.children[0].textContent;
            if (answer === droppable.dataset.answer) {
                correct++;
                droppable.style.backgroundColor = '#dff0d8';
            } else {
                droppable.style.backgroundColor = '#f2dede';
            }
        } else {
            droppable.style.backgroundColor = '#f2dede';
        }
    });
    
    document.getElementById('result').textContent = 
        `You got ${correct} out of ${total} correct!`;
}
</script>

<style>
#quiz-container {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    font-family: Arial, sans-serif;
}

#word-bank {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    padding: 15px;
    background-color: #f5f5f5;
    border-radius: 8px;
    margin-bottom: 20px;
}

.draggable {
    padding: 8px 12px;
    background-color: #4CAF50;
    color: white;
    border-radius: 4px;
    cursor: move;
    user-select: none;
}

.draggable.dragging {
    opacity: 0.5;
}

#sentences {
    line-height: 2;
}

.droppable {
    display: inline-block;
    width: 120px;
    min-height: 30px;
    border: 2px dashed #ccc;
    border-radius: 4px;
    margin: 0 5px;
    vertical-align: middle;
    padding: 4px;
}

button {
    display: block;
    margin: 20px 0;
    padding: 10px 20px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
}

button:hover {
    background-color: #45a049;
}

#result {
    margin-top: 15px;
    font-weight: bold;
    text-align: center;
}
</style>

Would you like me to explain how any part of this implementation works?
