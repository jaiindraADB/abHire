 document.getElementById('submit').addEventListener('click', async () => {
      const email = document.getElementById('username').value.trim();
      const password = document.getElementById('password').value.trim();
      const messageDiv = document.getElementById('message');

      messageDiv.textContent = '';

      if (!email || !password) {
        messageDiv.textContent = 'Please enter both email and password.';
        return;
      }

      try {
        const response = await axios.post('https://abhirebackend.onrender.com/auth/login', {
          email,
          password
        }, {
          headers: {
            'Content-Type': 'application/json'
          }
        });

        console.log('Login success:', response.data);
        messageDiv.className = 'success';
        messageDiv.textContent = 'Login successful!';
