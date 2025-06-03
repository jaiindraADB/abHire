<!-- navbar.md -->

[Home](/)
[Guide](/guide.md)
[Interview Scheduler](/interview-scheduler.md)
[About](/about.md)

Docsify automatically places the navbar.md contents at the top. To make the search bar visible in the navbar, use this CSS (in a <style> block in your index.html or a separate CSS file):

<style>
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: #f8f9fa;
  padding: 0.5rem 1rem;
}

.app-name {
  font-weight: bold;
  font-size: 1.2rem;
}

.search input {
  padding: 4px 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
