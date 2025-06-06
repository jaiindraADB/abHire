<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Login Page</title>
  <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
</head>
<body>
  <h2>Login Form</h2>
  <form id="loginForm">
    <label>Email: <input type="email" id="email" value="satya@adbinary.com" /></label><br>
    <label>Password: <input type="password" id="password" value="satya" /></label><br>
    <button type="submit">Login</button>
  </form>

  <script>
    const corsProxy = "https://cors-anywhere.herokuapp.com/";
    const apiURL = "https://abhirebackend.onrender.com/auth/login";

    document.getElementById('loginForm').addEventListener('submit', async function(e) {
      e.preventDefault();

      const email = document.getElementById("email").value;
      const password = document.getElementById("password").value;

      try {
        const response = await axios.post(corsProxy + apiURL, {
          email,
          password
        }, {
          headers: {
            "Content-Type": "application/json"
          }
        });

        console.log("✅ Login Success:", response.data);
        alert("Login successful. Token: " + response.data.token);

        // You can now store the token, redirect, or call another API
        // localStorage.setItem("token", response.data.token);
        // window.location.href = "/dashboard.html";

      } catch (error) {
        console.error("❌ Login Failed:", error);
        alert("Login failed: " + (error.response?.data?.message || error.message));
      }
    });
  </script>
  const corsProxy = "https://cors-anywhere.herokuapp.com/";
const apiURL = "https://abhirebackend.onrender.com/auth/login";

fetch(corsProxy + apiURL, {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    email: "satya@adbinary.com",
    password: "satya"
  })
})
.then(res => res.json())
.then(data => console.log("Login Success:", data))
.catch(err => console.error("Login Failed:", err));

</body>
</html>
