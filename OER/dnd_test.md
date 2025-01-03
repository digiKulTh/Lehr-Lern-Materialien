<!--
author:   Your Name
email:    your@email.com
version:  0.1.0
language: de
narrator: Deutsch Female

@DragDropQuiz
<script>
    let container = document.createElement('div');
    container.className = 'drag-drop-quiz';
    
    // Parse input parameters
    let items = '@0'.split(',');
    let correctOrder = [@1];
    
    // Add styles
    let style = document.createElement('style');
    style.textContent = `
        .drag-drop-quiz {
            margin: 20px 0;
        }
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
        }
        .draggable.dragging {
            opacity: 0.5;
        }
        .drop-zone {
            min-height: 50px;
            margin: 10px 0;
            padding: 10px;
            border: 2px dashed #ccc;
            border-radius: 5px;
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
        .feedback {
            margin-top: 10px;
            padding: 10px;
            border-radius: 4px;
            display: none;
        }
        .feedback.correct {
            display: block;
            background: #c8e6c9;
            color: #2e7d32;
        }
        .feedback.incorrect {
            display: block;
            background: #ffcdd2;
            color: #c62828;
        }
    `;
    container.appendChild(style);
    
    // Create drag container
    let dragContainer = document.createElement('div');
    dragContainer.className = 'drag-container';
    
    // Create drop zone
    let dropZone = document.createElement('div');
    dropZone.className = 'drop-zone';
    
    // Create draggable elements
    items.forEach((item, index) => {
        let draggable = document.createElement('div');
        draggable.className = 'draggable';
        draggable.draggable = true;
        draggable.textContent = item;
        draggable.dataset.index = index;
        dragContainer.appendChild(draggable);
    });
    
    // Create check button
    let checkButton = document.createElement('button');
    checkButton.className = 'check-button';
    checkButton.textContent = 'Antwort überprüfen';
    
    // Create feedback element
    let feedback = document.createElement('div');
    feedback.className = 'feedback';
    
    // Add drag and drop functionality
    dragContainer.addEventListener('dragstart', e => {
        if (e.target.classList.contains('draggable')) {
            e.target.classList.add('dragging');
        }
    });
    
    dragContainer.addEventListener('dragend', e => {
        if (e.target.classList.contains('draggable')) {
            e.target.classList.remove('dragging');
        }
    });
    
    dropZone.addEventListener('dragover', e => {
        e.preventDefault();
        const draggable = document.querySelector('.dragging');
        if (draggable) {
            dropZone.appendChild(draggable);
        }
    });
    
    // Add check functionality
    checkButton.addEventListener('click', () => {
        const currentOrder = Array.from(dropZone.children).map(child => 
            parseInt(child.dataset.index));
        const isCorrect = currentOrder.every((value, index) => 
            value === correctOrder[index]);
        
        feedback.textContent = isCorrect ? 
            'Richtig! Die Reihenfolge ist korrekt.' : 
            'Nicht ganz richtig. Versuchen Sie es noch einmal!';
        feedback.className = 'feedback ' + (isCorrect ? 'correct' : 'incorrect');
    });
    
    // Assemble quiz
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
