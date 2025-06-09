<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Modal with API Dropdown</title>
  <style>
    /* Basic styles for modal */
    .modal {
      display: none;
      position: fixed;
      z-index: 1000;
      left: 0; top: 0;
      width: 100%; height: 100%;
      background-color: rgba(0,0,0,0.5);
      justify-content: center;
      align-items: center;
    }

    .modal-content {
      background-color: #fff;
      padding: 20px;
      width: 300px;
      border-radius: 8px;
      text-align: center;
    }

    .btn {
      padding: 10px 15px;
      background-color: #007bff;
      color: white;
      border: none;
      cursor: pointer;
      border-radius: 5px;
    }

    .btn-close {
      background-color: #dc3545;
      margin-top: 10px;
    }

    select {
      width: 100%;
      padding: 8px;
      margin-top: 10px;
    }

    a {
      display: inline-block;
      margin-top: 15px;
      color: #007bff;
      text-decoration: underline;
    }
  </style>
</head>
<body>

  <!-- Button to open modal -->
  <button class="btn" onclick="openModal()">Open Modal</button>

  <!-- Modal HTML -->
  <div id="myModal" class="modal">
    <div class="modal-content">
      <h2>Select Priority</h2>

      <!-- Dropdown will be populated dynamically -->
      <select id="priorityDropdown">
        <option>Loading...</option>
      </select>

      <!-- Navigation Link -->
      <a href="next-page.html">Go to Next Page</a><br>

      <!-- Close Button -->
      <button class="btn btn-close" onclick="closeModal()">Close</button>
    </div>
  </div>

  <script>
    function openModal() {
      document.getElementById("myModal").style.display = "flex";
      loadDropdown();
    }

    function closeModal() {
      document.getElementById("myModal").style.display = "none";
    }

    function loadDropdown() {
      const dropdown = document.getElementById("priorityDropdown");
      dropdown.innerHTML = "<option>Loading...</option>";

      // Replace this with your actual API endpoint
      fetch("https://api.example.com/priority")
        .then(response => response.json())
        .then(data => {
          dropdown.innerHTML = "";
          data.forEach(item => {
            const option = document.createElement("option");
            option.value = item.value;
            option.text = item.label;
            dropdown.appendChild(option);
          });
        })
        .catch(error => {
          dropdown.innerHTML = "<option>Error loading data</option>";
          console.error("Dropdown API Error:", error);
        });
    }
  </script>

</body>
</html>
merge
react code to this
