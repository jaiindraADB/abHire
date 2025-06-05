<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
<script>
  const Userusername = document.getElementById('username');
  const Userpassword = document.getElementById('password');
  const submitbutton = document.getElementById('Submit');

  submitbutton.onclick = function () {
    const email = Userusername.value;
    const password = Userpassword.value;

    axios.post('https://abhirebackend.onrender.com/auth/login', {
      email,
      password
    }, {
      headers: {
        'Content-Type': 'application/json'
      }
    })
    .then(response => {
      console.log('Login successful:', response.data);
      // TODO: Store token or redirect user
      // localStorage.setItem('token', response.data.token);
    })
    .catch(error => {
      if (error.response) {
        console.error('Login failed:', error.response.data.message);
        alert('Login failed: ' + error.response.data.message);
      } else {
        console.error('Error:', error.message);
        alert('Unexpected error occurred');
      }
    });
  };
</script>
