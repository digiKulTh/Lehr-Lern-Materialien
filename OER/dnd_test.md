<!--
author:   Your Name
email:    your@email.com
version:  0.1.0
language: de
narrator: Deutsch Female

script:   https://storage.googleapis.com/lie-js/dragdrop.js

@DragDropQuiz
<script style="display: block" modify="false">
const quizContainer = "@uid";
const items = "@0".split(",");
const correctOrder = [@1];

// CSS Styles
const style = document.createElement('style');
style.textContent = `
.drag-container-${quizContainer} {
    margin: 20px 0;
    padding: 10px;
    background: #f5f5f5;
    border-radius: 5px;
}

.draggable-${quizContainer} {
    padding: 10px;
    margin: 5px;
    background: white;
    border: 1px solid #ccc;
    cursor: grab;
    user-select: none;
    border-radius: 3px;
    transition: background 0.2s;
}

.draggable-${quizContainer}:active {
    cursor: grabbing;
}

.draggable-${quizContainer}.dragging {
    opacity: 0.5;
    background: #e0e0e0;
}

.drop-zone-${quizContainer} {
    min-height: 50px;
    margin: 10px 0;
    padding: 10px;
    border: 2px dashed #ccc;
    border-radius: 5px;
}

.drop-zone-${quizContainer}.drag-over {
    background: #e1f5fe;
    border-color: #2196f3;
}

.check-button-${quizContainer} {
    margin-top: 10px;
    padding: 8px 16px;
    background: #2196f3;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.check-button-${quizContainer}:hover {
    background: #1976d2;
}

.feedback-${quizContainer} {
    margin-top: 10px;
    padding: 10px;
    border-radius: 4px;
}

.feedback-${quizContainer}.correct {
    background: #c8e6c9;
    color: #2e7d32;
}

.feedback-${quizContainer}.incorrect {
    background: #ffcdd2;
    color: #c62828;
}
`;
document.head.appendChild(style);

// Create container elements
const container = document.createElement('div');
const dragContainer = document.createElement('div');
dragContainer.className = `drag-container-${quizContainer}`;
const dropZone = document.createElement('div');
dropZone.className = `drop-zone-${quizContainer}`;

// Create draggable elements
const draggables = items.map((item, index) => {
    const div = document.createElement('div');
    div.className = `draggable-${quizContainer}`;
    div.draggable = true;
    div.textContent = item;
    div.dataset.index = index;
    return div;
});

// Randomize initial order
draggables.sort(() => Math.random() - 0.5);
draggables.forEach(div => dragContainer.appendChild(div));

// Create check button and feedback element
const checkButton = document.createElement('button');
checkButton.className = `check-button-${quizContainer}`;
checkButton.textContent = 'Antwort überprüfen';

const feedback = document.createElement('div');
feedback.className = `feedback-${quizContainer}`;

// Add drag and drop event listeners
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
    dropZone.classList.add('drag-over');
    const draggable = document.querySelector('.dragging');
    if (draggable) {
        const afterElement = getDragAfterElement(dropZone, e.clientY);
        if (afterElement) {
            dropZone.insertBefore(draggable, afterElement);
        } else {
            dropZone.appendChild(draggable);
        }
    }
});

dropZone.addEventListener('dragleave', () => {
    dropZone.classList.remove('drag-over');
});

dropZone.addEventListener('drop', () => {
    dropZone.classList.remove('drag-over');
});

function getDragAfterElement(container, y) {
    const draggableElements = [...container.querySelectorAll(`.draggable-${quizContainer}:not(.dragging)`)]
    
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

// Add check functionality
checkButton.addEventListener('click', () => {
    const currentOrder = Array.from(dropZone.children).map(child => parseInt(child.dataset.index));
    const isCorrect = currentOrder.every((value, index) => value === correctOrder[index]);
    
    feedback.textContent = isCorrect ? 
        'Richtig! Die Reihenfolge ist korrekt.' : 
        'Nicht ganz richtig. Versuchen Sie es noch einmal!';
    feedback.className = `feedback-${quizContainer} ${isCorrect ? 'correct' : 'incorrect'}`;
});

// Append all elements
container.appendChild(dragContainer);
container.appendChild(dropZone);
container.appendChild(checkButton);
container.appendChild(feedback);

return container;
</script>
@end
-->

# Drag & Drop Quiz Demo

Ordnen Sie die folgenden Schritte in der richtigen Reihenfolge an:

@DragDropQuiz(Objektauswahl,Zustandsdokumentation,Fotografische Erfassung,Metadateneingabe,Qualitätskontrolle|0,1,2,3,4)
