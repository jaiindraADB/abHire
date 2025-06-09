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
