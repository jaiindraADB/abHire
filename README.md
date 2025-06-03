<!-- navbar.md -->

[Home](/)
[Guide](/guide.md)
[Interview Scheduler](/interview-scheduler.md)
[About](/about.md)

Docsify automatically places the navbar.md contents at the top. To make the search bar visible in the navbar, use this CSS (in a <style> block in your index.html or a separate CSS file):

<!-- navbar.md -->

[Home](/)
[Jobs](/jobs.md)
[Candidates](/candidates.md)
[Reports](/reports.md)

<!-- Custom HTML inside navbar -->
<form class="navbar-search">
  <input type="text" id="customSearchInput" placeholder="Search..." />
</form>

<script>
  // Custom search logic for navbar input
  document.addEventListener('DOMContentLoaded', function () {
    const input = document.getElementById('customSearchInput');
    input?.addEventListener('keypress', function (e) {
      if (e.key === 'Enter') {
        e.preventDefault();
        const keyword = input.value.toLowerCase();
        const sidebarLinks = document.querySelectorAll('.sidebar a');
        for (const link of sidebarLinks) {
          const text = link.innerText.toLowerCase();
          if (text.includes(keyword)) {
            link.scrollIntoView({ behavior: 'smooth' });
            link.style.background = '#ffffcc';
            break;
          }
        }
      }
    });
  });
</script>

<style>
.navbar-search {
  display: inline-block;
  margin-left: 20px;
}

#customSearchInput {
  padding: 4px 8px;
  font-size: 14px;
  border-radius: 4px;
  border: 1px solid #ccc;
}
</style>
