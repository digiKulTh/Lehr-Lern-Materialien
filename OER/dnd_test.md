<!--
name: drag-drop-quiz
version: 0.0.1
-->

@DragDropQuiz
<script>
// CSS für die Drag & Drop Funktionalität
const style = document.createElement('style');
style.textContent = `
.drag-container {
    margin: 20px 0;
    padding: 10px;
    background: #f5f5f5;
    border-radius: 5px;
}

.draggable {
    padding: 10px;
    margin: 5px;
    background: white;
    border: 1px solid #ccc;
    cursor: grab;
    user-select: none;
    border-radius: 3px;
    transition: background 0.2s;
}

.draggable:active {
    cursor: grabbing;
}

.draggable.dragging {
    opacity: 0.5;
    background: #e0e0e0;
}

.drop-zone {
    min-height: 50px;
    margin: 10px 0;
    padding: 10px;
    border: 2px dashed #ccc;
    border-radius: 5px;
}

.drop-zone.drag-over {
    background: #e1f5fe;
    border-color: #2196f3;
}

.check-button {
    margin-top: 10px;
    padding: 8px 16px;
    background: #2196f3;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.check-button:hover {
    background: #1976d2;
}

.feedback {
    margin-top: 10px;
    padding: 10px;
    border-radius: 4px;
}

.feedback.correct {
    background: #c8e6c9;
    color: #2e7d32;
}

.feedback.incorrect {
    background: #ffcdd2;
    color: #c62828;
}
`;
document.head.appendChild(style);

// Hauptfunktion zur Erstellung des Drag & Drop Quiz
function createDragDropQuiz(container, items, correctOrder) {
    // Container für die verschiebbaren Elemente
    const dragContainer = document.createElement('div');
    dragContainer.className = 'drag-container';
    
    // Drop-Zone erstellen
    const dropZone = document.createElement('div');
    dropZone.className = 'drop-zone';
    
    // Elemente erstellen
    const draggables = items.map((item, index) => {
        const div = document.createElement('div');
        div.className = 'draggable';
        div.draggable = true;
        div.textContent = item;
        div.dataset.index = index;
        return div;
    });
    
    // Zufällige Anordnung der Elemente
    draggables.sort(() => Math.random() - 0.5);
    draggables.forEach(div => dragContainer.appendChild(div));
    
    // Prüf-Button erstellen
    const checkButton = document.createElement('button');
    checkButton.className = 'check-button';
    checkButton.textContent = 'Antwort überprüfen';
    
    // Feedback-Element erstellen
    const feedback = document.createElement('div');
    feedback.className = 'feedback';
    
    // Event Listeners für Drag & Drop
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
    
    // Hilfsfunktion zur Bestimmung der Einfügeposition
    function getDragAfterElement(container, y) {
        const draggableElements = [...container.querySelectorAll('.draggable:not(.dragging)')]
        
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
    
    // Prüf-Funktion
    checkButton.addEventListener('click', () => {
        const currentOrder = Array.from(dropZone.children).map(child => parseInt(child.dataset.index));
        const isCorrect = currentOrder.every((value, index) => value === correctOrder[index]);
        
        feedback.textContent = isCorrect ? 
            'Richtig! Die Reihenfolge ist korrekt.' : 
            'Nicht ganz richtig. Versuchen Sie es noch einmal!';
        feedback.className = `feedback ${isCorrect ? 'correct' : 'incorrect'}`;
    });
    
    // Alles zusammenfügen
    container.appendChild(dragContainer);
    container.appendChild(dropZone);
    container.appendChild(checkButton);
    container.appendChild(feedback);
}

// LiaScript Macro
@add_html
<div id="quiz-container"></div>
<script>
const items = ['@0'.split(',')];
const correctOrder = [@1];
createDragDropQuiz(
    document.getElementById('quiz-container'),
    items,
    correctOrder
);
</script>
@end

# Demo
## section 1

@DragDropQuiz(Objektauswahl,Zustandsdokumentation,Fotografische Erfassung,Metadateneingabe,Qualitätskontrolle|0,1,2,3,4)
