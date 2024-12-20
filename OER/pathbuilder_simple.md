# test

  <div class="container">
    <h2>Year + 70 Calculator</h2>
    <label for="yearInput">Enter a year:</label>
    <input type="number" id="yearInput" placeholder="Enter a year (e.g., 2024)">
    <div class="output" id="output"></div>
  </div>

  <script>
    // Get references to the input field and output div
    const yearInput = document.getElementById('yearInput');
    const output = document.getElementById('output');

    // Add an event listener to update the output as the user types
    yearInput.addEventListener('input', () => {
      const year = parseInt(yearInput.value); // Parse the input as an integer
      if (!isNaN(year)) {
        // If the input is a valid number, calculate and display the year + 70
        output.textContent = `Year + 70: ${year + 70}`;
      } else {
        // If the input is invalid, clear the output
        output.textContent = '';
      }
    });
  </script>
