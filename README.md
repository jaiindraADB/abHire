<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Hiring Flow Table</title>
  <style>
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 20px;
    }
    th, td {
      border: 1px solid #cccccc;
      padding: 10px;
      text-align: left;
    }
    th {
      background-color: #f3f3f3;
    }
    #loadBtn {
      padding: 10px 20px;
      font-size: 16px;
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <button id="loadBtn" onclick="loadTableData()">Load Hiring Flow Steps</button>

  <div id="tableContainer">
    <!-- Table will render here -->
  </div>

  <script>
    function loadTableData() {
      const container = document.getElementById("tableContainer");
      container.innerHTML = "<p>Loading...</p>";

      fetch("https://api.example.com/hiringflow/steps") // Replace with your actual API
        .then(response => response.json())
        .then(data => {
          if (!Array.isArray(data) || data.length === 0) {
            container.innerHTML = "<p>No data found.</p>";
            return;
          }

          const table = document.createElement("table");
          const thead = document.createElement("thead");
          const headerRow = document.createElement("tr");

          // Define the keys to show (in order)
          const headers = [
            "hiringflow_steps_master_id",
            "step_name",
            "step_code",
            "description",
            "step_level",
            "is_configurable",
            "is_active",
            "created_at"
          ];

          headers.forEach(key => {
            const th = document.createElement("th");
            th.textContent = key.replace(/_/g, " ").toUpperCase();
            headerRow.appendChild(th);
          });

          thead.appendChild(headerRow);
          table.appendChild(thead);

          const tbody = document.createElement("tbody");

          data.forEach(item => {
            const row = document.createElement("tr");

            headers.forEach(key => {
              const td = document.createElement("td");
              let value = item[key];

              // Format booleans as Yes/No
              if (typeof value === "boolean") {
                value = value ? "Yes" : "No";
              }

              // Truncate ISO datetime
              if (key === "created_at" && typeof value === "string") {
                value = new Date(value).toLocaleString();
              }

              td.textContent = value ?? "-";
              row.appendChild(td);
            });

            tbody.appendChild(row);
          });

          table.appendChild(tbody);
          container.innerHTML = ""; // Clear loading
          container.appendChild(table);
        })
        .catch(error => {
          console.error("API Error:", error);
          container.innerHTML = "<p style='color:red;'>Failed to load data.</p>";
        });
    }
  </script>

</body>
</html>
