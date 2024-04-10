<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Email Login</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Email Login</h1>
        <form id="login-form">
            <label for="email">Email address</label>
            <input type="email" id="email" name="email" required>

            <label for="password">Password</label>
            <input type="password" id="password" name="password" required>

            <button type="submit">Sign in</button>
        </form>
        <p>Don't have an account? <a href="#" id="signup-link">Create one</a></p>
    </div>
</body>
</html>
