<script>
    const loginForm = document.getElementById('loginForm');
    const messageDiv = document.getElementById('message');

    loginForm.addEventListener('submit', async (e) => {
      e.preventDefault();

      const email = document.getElementById('email').value.trim();
      const password = document.getElementById('password').value;

      try {
        const response = await fetch('https://abhirebackend.onrender.com/auth/login', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({ email, password })
        });

        const data = await response.json();
        console.log(data);

        if (response.ok) {
          messageDiv.textContent = `Welcome, ${data.user.name || email}!`;
          messageDiv.style.color = 'green';
          // Optionally, redirect or store token:
          // localStorage.setItem("token", data.token);
          // window.location.href = "/dashboard.html";
        } else {
          messageDiv.textContent = data.message || 'Login failed.';
          messageDiv.style.color = 'red';
        }

      } catch (err) {
        console.error(err);
        messageDiv.textContent = 'Server error. Please try again.';
        messageDiv.style.color = 'red';
      }
    });
  </script>
