<!-- Include Docsify core and search plugin -->
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>

<script>
  window.$docsify = {
    name: 'My Documentation',
    loadNavbar: true,
    search: {
      paths: 'auto',
      placeholder: '🔍 Search...',
      noData: 'No results!',
      depth: 2,
    }
  };
</script>

<script>
  document.addEventListener('DOMContentLoaded', function () {
    setTimeout(() => {
      const searchBox = document.querySelector('.search input');
      if (searchBox) {
        const navbar = document.querySelector('nav');
        const clone = searchBox.cloneNode(true);
        clone.placeholder = '🔍 Search Docs';
        clone.style.marginLeft = '20px';
        navbar.appendChild(clone);
      }
    }, 1000); // wait for search to load
  });
</script>
