<script>
document.addEventListener('DOMContentLoaded', function () {
  setTimeout(() => {
    const originalSearchBox = document.querySelector('.search input');
    const navbar = document.querySelector('nav');
    
    if (originalSearchBox && navbar) {
      const clonedInput = originalSearchBox.cloneNode(true);
      clonedInput.classList.add('nav-search');
      navbar.appendChild(clonedInput);

      // SYNC: Trigger search via sidebar input
      clonedInput.addEventListener('input', function () {
        originalSearchBox.value = clonedInput.value;
        const event = new Event('input', { bubbles: true });
        originalSearchBox.dispatchEvent(event);
      });
    }
  }, 800); // Ensure DOM and search plugin are ready
});
</script>
