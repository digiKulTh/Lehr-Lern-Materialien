<!--
author:   Your Name
email:    your@email.com
version:  0.1.0
language: de
narrator: Deutsch Female

********************************************************************************
**Extension: DragAndDropQuiz**
********************************************************************************

<script>
/**
 * Dieses Skript fügt eine einfache Drag-and-Drop-Quiz-Komponente hinzu.
 * Idee: 
 *  - Man kann Items per Drag & Drop in die korrekte Reihenfolge bringen.
 *  - Eine "Prüfen"-Schaltfläche vergleicht die Reihenfolge mit der erwarteten Lösung.
 * 
 * Integration ins LiaScript:
 *  - Mit @DragAndDropQuiz können einzelne Aufgaben definiert werden.
 *  - Die Aufgaben enthalten sowohl die zu sortierenden Elemente als auch eine "list"-Definition
 *    mit dem korrekten Ziel-Array.
 */

let DragAndDropQuiz = {
  // Initiales Rendering des HTML-Inhalts
  init: function(container, taskData) {
    // taskData enthält unsere Daten aus dem LiaScript-Block
    let { question, items, solution } = taskData;

    container.innerHTML = `
      <div class="drag-and-drop-container">
        <p><strong>${question}</strong></p>
        <div class="dd-list" id="dd-list"></div>
        <button id="checkBtn">Prüfen</button>
        <div id="resultMsg"></div>
      </div>
    `;

    // Elemente einfügen
    let ddList = container.querySelector("#dd-list");
    items.forEach((item, idx) => {
      let el = document.createElement("div");
      el.classList.add("dd-item");
      el.setAttribute("draggable", "true");
      el.setAttribute("data-index", idx);
      el.innerText = item;
      ddList.appendChild(el);
    });

    // Drag & Drop Behavior
    let draggedEl = null;

    ddList.addEventListener("dragstart", (e) => {
      if (e.target.classList.contains("dd-item")) {
        draggedEl = e.target;
        e.dataTransfer.effectAllowed = "move";
        e.dataTransfer.setData("text/plain", e.target.innerText);
      }
    });

    ddList.addEventListener("dragover", (e) => {
      e.preventDefault();
      let target = e.target;
      if (target && target.classList.contains("dd-item") && target !== draggedEl) {
        // Für den Effekt: beim Überfahren "aktiv" setzen
      }
    });

    ddList.addEventListener("drop", (e) => {
      e.preventDefault();
      let target = e.target;
      if (target && target.classList.contains("dd-item") && target !== draggedEl) {
        // Die Positionen der Elemente vertauschen
        let draggedIndex = draggedEl.getAttribute("data-index");
        let targetIndex = target.getAttribute("data-index");

        // Im DOM austauschen
        let draggedHTML = draggedEl.outerHTML;
        let targetHTML = target.outerHTML;
        draggedEl.outerHTML = targetHTML;
        target.outerHTML = draggedHTML;

        // Neue refs zu den ausgetauschten Elementen holen (nach dem outerHTML-Swap)
        let ddItems = ddList.querySelectorAll(".dd-item");
        ddItems.forEach((el, i) => {
          el.setAttribute("data-index", i);
        });
      }
    });

    // "Prüfen"-Button
    container.querySelector("#checkBtn").addEventListener("click", () => {
      let userOrder = [];
      ddList.querySelectorAll(".dd-item").forEach((el) => {
        userOrder.push(el.innerText.trim());
      });
      let resultMsg = container.querySelector("#resultMsg");

      if (JSON.stringify(userOrder) === JSON.stringify(solution)) {
        resultMsg.innerHTML = `<p style="color:green;">Richtig!</p>`;
      } else {
        resultMsg.innerHTML = `<p style="color:red;">Falsch. Versuche es nochmal.</p>`;
      }
    });
  }
};


// LiaScript Hook, damit das Plugin verwendet werden kann
export default {
  // Der Schlüssel, unter dem das Plugin verfügbar ist (z.B. @DragAndDropQuiz)
  tag: "DragAndDropQuiz",
  
  // Daten aus dem LiaScript-Block (Markdown) verarbeiten
  parse: function(raw) {
    // raw = vollständiger Inhalt zwischen @DragAndDropQuiz ... @DragAndDropQuiz
    // Beispiel: question=..., items=..., solution=[...]
    
    let data = {
      question: "",
      items: [],
      solution: []
    };

    // Einfaches Parsen über Zeilen (minimalistischer Ansatz)
    // Erlaubt ein Format wie:
    //
    // question=Wie lautet die richtige Reihenfolge?
    // items=Erstes, Zweites, Drittes, Viertes
    // solution=Erstes, Zweites, Drittes, Viertes
    //
    // Wichtig: Komma-getrennte Elemente in Arrays umwandeln.

    let lines = raw.trim().split("\n");
    for (let line of lines) {
      let trimmed = line.trim();
      if (trimmed.startsWith("question=")) {
        data.question = trimmed.replace("question=", "").trim();
      } else if (trimmed.startsWith("items=")) {
        let itemsText = trimmed.replace("items=", "").trim();
        data.items = itemsText.split(",").map(i => i.trim());
      } else if (trimmed.startsWith("solution=")) {
        let solText = trimmed.replace("solution=", "").trim();
        data.solution = solText.split(",").map(i => i.trim());
      }
    }
    return data;
  },

  // Wird aufgerufen, wenn der Block gerendert wird
  render: function(root, data) {
    DragAndDropQuiz.init(root, data);
  }
};
</script>
-->

# Drag & Drop Quiz Demo

Ordnen Sie die folgenden Schritte in der richtigen Reihenfolge an:

@DragAndDropQuiz
question=Bringe die Elemente in die richtige Reihenfolge.
items=Mars, Venus, Merkur, Jupiter
solution=Merkur, Venus, Mars, Jupiter
@DragAndDropQuiz
