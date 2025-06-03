<!-- Docsify setup -->
<script>
  window.$docsify = {
    name: 'Your Docs',
    repo: '',
    loadNavbar: true,
    search: 'auto', // Optional: only if using built-in search
  };
</script>
<script src="//unpkg.com/docsify/lib/docsify.min.js"></script>

<!-- Custom script for navbar search -->
<script>
  function handleNavbarSearch(event) {
    if (event.key === 'Enter') {
      event.preventDefault();
      const keyword = event.target.value.trim().toLowerCase();
      if (!keyword) return;

      // Simulate search: highlight first matching sidebar link
      const sidebarLinks = document.querySelectorAll('.sidebar a');
      for (let link of sidebarLinks) {
        const text = link.textContent.trim().toLowerCase();
        if (text.includes(keyword)) {
          link.scrollIntoView({ behavior: 'smooth', block: 'center' });
          link.style.backgroundColor = '#ffe58a';
          break;
        }
      }
    }
  }
</script>

<!-- Style the navbar search input -->
<style>
  #nav-search-form {
    display: inline-block;
    margin-left: 20px;
  }

  #nav-search-input {
    padding: 5px 10px;
    font-size: 14px;
    border-radius: 5px;
    border: 1px solid #ccc;
    background-color: white;
  }

  nav.app-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>
