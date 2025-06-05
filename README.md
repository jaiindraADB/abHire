axios.post('https://abhirebackend.onrender.com/auth/login', {
  email: 'satya@adbinary.com',
  password: 'satya'
}, {
  headers: {
    'Content-Type': 'application/json'
  }
})
.then(response => {
  console.log('Login success:', response.data);
})
.catch(error => {
  if (error.response) {
    console.error('Login failed:', error.response.data);
  } else {
    console.error('Network/CORS error:', error.message);
  }
});
