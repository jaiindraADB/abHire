<!-- Docsify core -->
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>

<!-- Fuse.js for fuzzy searching -->
<script src="https://cdn.jsdelivr.net/npm/fuse.js@6.6.2"></script>

<script>
  window.$docsify = {
    name: "Job Portal",
    loadSidebar: true,
    search: false, // Disable default search
    plugins: [
      function(hook, vm) {
        let fuse;
        let searchData = [];

        hook.ready(async function () {
          const res = await fetch('searchIndex.json');
          searchData = await res.json();
          fuse = new Fuse(searchData, {
            keys: ['title', 'content'],
            includeScore: true,
            threshold: 0.3
          });
        });

        hook.mounted(function () {
          const main = document.getElementById('main');

          // Add search input manually
          const input = document.createElement('input');
          input.setAttribute('type', 'search');
          input.setAttribute('placeholder', 'Search...');
          input.className = "custom-search";
          document.body.insertBefore(input, main);

          input.addEventListener('input', function () {
            const query = input.value.trim();
            if (!query || !fuse) return;

            const results = fuse.search(query);
            if (results.length > 0) {
              main.innerHTML = `<h2>Search Results for "${query}"</h2><ul>` +
                results.map(({ item }) =>
                  `<li><a href="${item.url}">${item.title}</a><br/><small>${item.content}</small></li>`
                ).join('') +
                '</ul>';
            } else {
              main.innerHTML = `<p>No results found for "${query}".</p>`;
            }
          });
        });
      }
    ]
  };
</script>

<style>
  .custom-search {
    width: 60%;
    margin: 20px auto;
    display: block;
    padding: 10px;
    font-size: 16px;
    border-radius: 6px;
    border: 1px solid #ccc;
  }
</style>
