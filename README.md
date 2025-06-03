<script>
  window.$docsify = {
    search: {
      paths: 'auto',
      placeholder: 'Search...',
      noData: 'No results!',
      depth: 3,
      hideOtherSidebarContent: false,
    },
    plugins: [
      function (hook, vm) {
        hook.mounted(function () {
          const searchInput = document.getElementById('custom-search') || document.querySelector('input[type=search]');
          const mainContainer = document.getElementById('main');

          if (searchInput) {
            searchInput.addEventListener('input', function (e) {
              const query = e.target.value.trim();
              if (query.length === 0) return;

              const results = window.DocsifySearch?.search?.getResults(query) || [];

              if (results.length > 0) {
                mainContainer.innerHTML = `<h2>Search Results for "${query}"</h2><ul>` +
                  results.map(r => `<li><a href="${r.url}">${r.title}</a><br/><small>${r.content}</small></li>`).join('') +
                  '</ul>';
              } else {
                mainContainer.innerHTML = `<p>No results found for "${query}".</p>`;
              }
            });
          }
        });
      }
    ]
  };
</script>
