[Home](/)
[Jobs](/jobs.md)
[Candidates](/candidates.md)
[Reports](/reports.md)

<!-- Search input -->
<input
  type="text"
  id="nav-page-search"
  placeholder="🔍 Search Pages..."
  oninput="filterPageSuggestions(this.value)"
  onkeydown="handleSearchEnter(event)"
  autocomplete="off"
/>
<div id="page-suggestions" class="suggestion-box"></div>

<script>
  // Define your searchable pages
  const pageList = [
    { title: "Home", path: "/" },
    { title: "Jobs", path: "/jobs.md" },
    { title: "Candidates", path: "/candidates.md" },
    { title: "Reports", path: "/reports.md" },
    { title: "Schedule Interview", path: "/schedule-interview.md" },
    { title: "Company Info", path: "/company-info.md" },
    { title: "Hiring Panel", path: "/hiring-panel.md" },
    { title: "User Profile", path: "/user-profile.md" }
    // Add more as needed
  ];

  function filterPageSuggestions(keyword) {
    const box = document.getElementById("page-suggestions");
    box.innerHTML = "";
    if (!keyword) return;

    const matches = pageList.filter(p =>
      p.title.toLowerCase().includes(keyword.toLowerCase())
    );

    matches.forEach(match => {
      const div = document.createElement("div");
      div.className = "suggestion-item";
      div.textContent = match.title;
      div.onclick = () => {
        location.hash = match.path;
        box.innerHTML = "";
        document.getElementById("nav-page-search").value = "";
      };
      box.appendChild(div);
    });
  }

  function handleSearchEnter(event) {
    if (event.key === "Enter") {
      const keyword = event.target.value.toLowerCase();
      const match = pageList.find(p =>
        p.title.toLowerCase().includes(keyword)
      );
      if (match) {
        location.hash = match.path;
        document.getElementById("page-suggestions").innerHTML = "";
      }
    }
  }
</script>

<style>
  #nav-page-search {
    padding: 5px 10px;
    font-size: 14px;
    border-radius: 5px;
    border: 1px solid #ccc;
    margin-left: 15px;
    background-color: white;
  }

  .suggestion-box {
    position: absolute;
    background: white;
    border: 1px solid #ccc;
    width: 200px;
    max-height: 200px;
    overflow-y: auto;
    z-index: 1000;
  }

  .suggestion-item {
    padding: 5px 10px;
    cursor: pointer;
  }

  .suggestion-item:hover {
    background-color: #f0f0f0;
  }
</style>
