<!--
author:   Your Name
email:    your@email.com
version:  0.1.0
language: de
narrator: Deutsch Female

@DragDropQuiz: @_dragdrop_quiz(@0, @1)

@_dragdrop_quiz
function(items, correctOrderStr) {
  let correctOrder = JSON.parse("[" + correctOrderStr + "]");
  let itemList = items.split(',');
  
  return `
  <div id="quiz-${@uid}" class="drag-drop-quiz">
    <style>
      .drag-drop-quiz {
        margin: 20px 0;
      }
      .drag-container-${@uid} {
        margin: 20px 0;
        padding: 10px;
        background: #f5f5f5;
        border-radius: 5px;
      }
      .draggable-${@uid} {
        padding: 10px;
        margin: 5px;
        background: white;
        border: 1px solid #ccc;
        cursor: grab;
        user-select: none;
        border-radius: 3px;
        transition: background 0.2s;
      }
      .draggable-${@uid}:active {
        cursor: grabbing;
      }
      .draggable-${@uid}.dragging {
        opacity: 0.5;
        background: #e0e0e0;
      }
      .drop-zone-${@uid} {
        min-height: 50px;
        margin: 10px 0;
        padding: 10px;
        border: 2px dashed #ccc;
        border-radius: 5px;
      }
      .drop-zone-${@uid}.drag-over {
        background: #e1f5fe;
        border-color: #2196f3;
      }
      .check-button-${@uid} {
        margin-top: 10px;
        padding: 8px 16px;
        background: #2196f3;
        color: white;
        border: none;
        border-radius: 4px;
        cursor: pointer;
      }
      .check-button-${@uid}:hover {
        background: #1976d2;
      }
      .feedback-${@uid} {
        margin-top: 10px;
        padding: 10px;
        border-radius: 4px;
        display: none;
      }
      .feedback-${@uid}.correct {
        display: block;
        background: #c8e6c9;
        color: #2e7d32;
      }
      .feedback-${@uid}.incorrect {
        display: block;
        background: #ffcdd2;
        color: #c62828;
      }
    </style>
    
    <div class="drag-container-${@uid}"></div>
    <div class="drop-zone-${@uid}"></div>
    <button class="check-button-${@uid}">Antwort überprüfen</button>
    <div class="feedback-${@uid}"></div>
    
    <script>
      (function() {
        const container = document.getElementById('quiz-${@uid}');
        const dragContainer = container.querySelector('.drag-container-${@uid}');
        const dropZone = container.querySelector('.drop-zone-${@uid}');
        const checkButton = container.querySelector('.check-button-${@uid}');
        const feedback = container.querySelector('.feedback-${@uid}');
        
        const items = ${JSON.stringify(itemList)};
        const correctOrder = ${JSON.stringify(correctOrder)};
        
        // Create draggable elements
        const draggables = items.map((item, index) => {
          const div = document.createElement('div');
          div.className = 'draggable-${@uid}';
          div.draggable = true;
          div.textContent = item;
          div.dataset.index = index;
          return div;
        });
        
        // Randomize initial order
        draggables.sort(() => Math.random() - 0.5);
        draggables.forEach(div => dragContainer.appendChild(div));
        
        // Drag and drop functionality
        draggables.forEach(draggable => {
          draggable.addEventListener('dragstart', () => {
            draggable.classList.add('dragging');
          });
          
          draggable.addEventListener('dragend', () => {
            draggable.classList.remove('dragging');
          });
        });
        
        dropZone.addEventListener('dragover', e => {
          e.preventDefault();
          const draggable = container.querySelector('.dragging');
          if (draggable) {
            const afterElement = getDragAfterElement(dropZone, e.clientY);
            if (afterElement) {
              dropZone.insertBefore(draggable, afterElement);
            } else {
              dropZone.appendChild(draggable);
            }
          }
        });
        
        function getDragAfterElement(container, y) {
          const draggableElements = [...container.querySelectorAll('.draggable-${@uid}:not(.dragging)')]
          
          return draggableElements.reduce((closest, child) => {
            const box = child.getBoundingClientRect();
            const offset = y - box.top - box.height / 2;
            
            if (offset < 0 && offset > closest.offset) {
              return { offset: offset, element: child };
            } else {
              return closest;
            }
          }, { offset: Number.NEGATIVE_INFINITY }).element;
        }
        
        // Check functionality
        checkButton.addEventListener('click', () => {
          const currentOrder = Array.from(dropZone.children).map(child => 
            parseInt(child.dataset.index));
          const isCorrect = currentOrder.every((value, index) => 
            value === correctOrder[index]);
          
          feedback.textContent = isCorrect ? 
            'Richtig! Die Reihenfolge ist korrekt.' : 
            'Nicht ganz richtig. Versuchen Sie es noch einmal!';
          feedback.className = 'feedback-${@uid} ' + (isCorrect ? 'correct' : 'incorrect');
        });
      })();
    </script>
  </div>`;
}
@end
-->

# Drag & Drop Quiz Demo

Ordnen Sie die folgenden Schritte in der richtigen Reihenfolge an:

@DragDropQuiz(Objektauswahl,Zustandsdokumentation,Fotografische Erfassung,Metadateneingabe,Qualitätskontrolle|0,1,2,3,4)
