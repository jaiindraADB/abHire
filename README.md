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
      function(hook, vm) {
        hook.mounted(function() {
          const searchInput = document.querySelector('input[type=search]');
          const mainContainer = document.getElementById('main');

          if (searchInput) {
            searchInput.addEventListener('input', async function(e) {
              const query = e.target.value.trim();
              if (query.length === 0) return;

              const result = window.DocsifySearch?.search?.getResults(query) || [];

              if (result.length > 0) {
                mainContainer.innerHTML = `<h2>Search Results for "${query}"</h2><ul>` +
                  result.map(r => `<li><a href="${r.url}">${r.title}</a> - <small>${r.content}</small></li>`).join('') +
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
