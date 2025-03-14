<!-- @format -->

<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>Voting System - Login/Register</title>
		<!-- Font Awesome -->
		<link
			rel="stylesheet"
			href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
		<!-- Google Fonts - Poppins -->
		<link
			href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap"
			rel="stylesheet" />
		<!-- SweetAlert2 -->
		<link
			rel="stylesheet"
			href="https://cdnjs.cloudflare.com/ajax/libs/limonte-sweetalert2/11.7.5/sweetalert2.min.css" />
		<style>
			* {
				margin: 0;
				padding: 0;
				box-sizing: border-box;
				font-family: "Poppins", sans-serif;
			}

			:root {
				--primary-color: #3a86ff;
				--primary-hover: #2667cc;
				--primary-light: rgba(58, 134, 255, 0.2);
				--bg-dark: #121212;
				--card-bg: #1e1e1e;
				--text-light: #e0e0e0;
				--text-secondary: #aaaaaa;
				--input-bg: #2c2c2c;
				--input-border: #444444;
				--shadow: 0 8px 24px rgba(0, 0, 0, 0.4);
				--transition: all 0.3s ease;
				--success: #4ade80;
				--warning: #fbbf24;
				--danger: #f87171;
			}

			body {
				background: linear-gradient(135deg, #1a1a1a 0%, #0f172a 100%);
				min-height: 100vh;
				display: flex;
				align-items: center;
				justify-content: center;
				padding: 20px;
				color: var(--text-light);
			}

			.container {
				display: flex;
				background: var(--card-bg);
				border-radius: 16px;
				box-shadow: var(--shadow);
				overflow: hidden;
				width: 100%;
				max-width: 1200px;
				min-height: 680px;
			}

			.center-content {
				width: 100%;
				padding: 40px;
				display: flex;
				justify-content: space-between;
				flex-wrap: wrap;
				gap: 30px;
			}

			.form-section {
				flex: 1;
				min-width: 320px;
				background: rgba(0, 0, 0, 0.2);
				border-radius: 12px;
				padding: 30px;
				position: relative;
				overflow: hidden;
				border: 1px solid rgba(255, 255, 255, 0.05);
				backdrop-filter: blur(5px);
			}

			.form-section::before {
				content: "";
				position: absolute;
				top: -50%;
				left: -50%;
				width: 200%;
				height: 200%;
				background-image: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z' fill='%233a86ff' fill-opacity='0.05' fill-rule='evenodd'/%3E%3C/svg%3E");
				opacity: 0.2;
				z-index: 0;
			}

			.logo {
				text-align: center;
				margin-bottom: 10px;
				width: 100%;
			}

			.logo h1 {
				font-size: 1.5rem;
				font-weight: 600;
				color: var(--primary-color);
				letter-spacing: 1px;
				margin-bottom: 10px;
			}

			.logo p {
				color: var(--text-secondary);
				font-size: 0.9rem;
			}

			.form-title {
				margin-bottom: 25px;
				position: relative;
				z-index: 1;
				color: var(--text-light);
			}

			.form-title h2 {
				font-size: 1.8rem;
				font-weight: 600;
				margin-bottom: 5px;
			}

			.form-title p {
				color: var(--text-secondary);
				font-size: 0.9rem;
			}

			.form-group {
				margin-bottom: 20px;
				position: relative;
				z-index: 1;
			}

			.form-group i {
				position: absolute;
				left: 15px;
				top: 50%;
				transform: translateY(-50%);
				color: var(--text-secondary);
			}

			.form-group input {
				width: 100%;
				padding: 15px 15px 15px 45px;
				background-color: var(--input-bg);
				border: 1px solid var(--input-border);
				border-radius: 8px;
				font-size: 1rem;
				color: var(--text-light);
				transition: var(--transition);
			}

			.form-group input:focus {
				border-color: var(--primary-color);
				box-shadow: 0 0 0 3px var(--primary-light);
				outline: none;
			}

			.form-group input::placeholder {
				color: var(--text-secondary);
			}

			.password-toggle {
				position: absolute;
				right: 15px;
				top: 50%;
				transform: translateY(-50%);
				cursor: pointer;
				color: var(--text-secondary);
				z-index: 2;
			}

			.strength-meter {
				height: 4px;
				background-color: rgba(255, 255, 255, 0.1);
				margin-top: 8px;
				border-radius: 2px;
			}

			.strength-meter div {
				height: 100%;
				border-radius: 2px;
				transition: var(--transition);
				width: 0;
			}

			.strength-text {
				font-size: 0.75rem;
				margin-top: 5px;
				color: var(--text-secondary);
			}

			.checkbox-group {
				display: flex;
				align-items: center;
				margin-bottom: 20px;
				position: relative;
				z-index: 1;
			}

			.checkbox-group input {
				margin-right: 10px;
				width: 16px;
				height: 16px;
				accent-color: var(--primary-color);
			}

			.checkbox-group label {
				font-size: 0.9rem;
				color: var(--text-secondary);
			}

			.checkbox-group a,
			.forgot-password {
				color: var(--primary-color);
				text-decoration: none;
				transition: var(--transition);
			}

			.checkbox-group a:hover,
			.forgot-password:hover {
				text-decoration: underline;
			}

			.forgot-password {
				display: block;
				text-align: right;
				margin-top: -10px;
				margin-bottom: 20px;
				font-size: 0.85rem;
				position: relative;
				z-index: 1;
			}

			.btn {
				width: 100%;
				padding: 15px;
				border: none;
				border-radius: 8px;
				background-color: var(--primary-color);
				color: white;
				font-size: 1rem;
				font-weight: 500;
				cursor: pointer;
				transition: var(--transition);
				margin-bottom: 20px;
				display: flex;
				justify-content: center;
				align-items: center;
				position: relative;
				z-index: 1;
				overflow: hidden;
			}

			.btn:hover {
				background-color: var(--primary-hover);
			}

			.btn i {
				margin-right: 10px;
			}

			.btn::before {
				content: "";
				position: absolute;
				top: 0;
				left: -100%;
				width: 100%;
				height: 100%;
				background: linear-gradient(
					90deg,
					transparent,
					rgba(255, 255, 255, 0.2),
					transparent
				);
				transition: 0.5s;
			}

			.btn:hover::before {
				left: 100%;
			}

			.social-login {
				margin-top: 20px;
				text-align: center;
				position: relative;
				z-index: 1;
			}

			.social-login p {
				color: var(--text-secondary);
				margin-bottom: 15px;
				position: relative;
				display: flex;
				align-items: center;
				justify-content: center;
			}

			.social-login p::before,
			.social-login p::after {
				content: "";
				flex: 1;
				height: 1px;
				background-color: var(--input-border);
				margin: 0 10px;
			}

			.google-btn {
				background-color: transparent;
				color: var(--text-light);
				border: 1px solid var(--input-border);
			}

			.google-btn:hover {
				background-color: rgba(255, 255, 255, 0.05);
			}

			.form-switch {
				text-align: center;
				margin-top: 20px;
				font-size: 0.9rem;
				color: var(--text-secondary);
				position: relative;
				z-index: 1;
				display: none;
			}

			.form-switch a {
				color: var(--primary-color);
				text-decoration: none;
				font-weight: 500;
				transition: var(--transition);
			}

			.form-switch a:hover {
				text-decoration: underline;
			}

			/* Benefits section */
			.benefits {
				list-style: none;
				margin-top: 20px;
				position: relative;
				z-index: 1;
			}

			.benefits li {
				margin-bottom: 15px;
				display: flex;
				align-items: center;
			}

			.benefits li i {
				margin-right: 10px;
				font-size: 1.2rem;
				color: var(--primary-color);
			}

			/* Mobile Responsiveness */
			@media (max-width: 968px) {
				.center-content {
					flex-direction: column;
					gap: 20px;
				}

				.form-section {
					min-width: 100%;
				}

				.form-switch {
					display: block;
				}
			}

			/* Glow Effect */
			.glow {
				position: absolute;
				width: 150px;
				height: 150px;
				background: var(--primary-color);
				border-radius: 50%;
				filter: blur(40px);
				opacity: 0.15;
				z-index: 0;
			}

			.glow-1 {
				top: -30px;
				left: -30px;
			}

			.glow-2 {
				bottom: -30px;
				right: -30px;
			}
		</style>
	</head>
	<body>
		<div class="container">
			<div class="center-content">
				<div class="logo">
					<h1><i class="fas fa-vote-yea"></i> SECURE VOTING SYSTEM</h1>
					<p>Your secure platform for digital democracy</p>
				</div>

				<!-- Login Form Section -->
				<div class="form-section">
					<div class="glow glow-1"></div>
					<div class="form-title">
						<h2>Secure Login</h2>
						<p>Your voice, your power!</p>
					</div>
					<form id="loginForm">
						<div class="form-group">
							<i class="fas fa-user"></i>
							<input
								type="text"
								id="login-username"
								placeholder="Email or Username"
								required />
						</div>
						<div class="form-group">
							<i class="fas fa-lock"></i>
							<input
								type="password"
								id="login-password"
								placeholder="Password"
								required />
							<i
								class="fas fa-eye-slash password-toggle"
								id="login-password-toggle"></i>
						</div>
						<div class="checkbox-group">
							<input type="checkbox" id="remember" />
							<label for="remember">Remember me</label>
						</div>
						<a href="#" class="forgot-password">Forgot Password?</a>
						<button type="submit" class="btn">
							<i class="fas fa-sign-in-alt"></i> Login
						</button>
					</form>
					<div class="social-login">
						<p>Or login with</p>
						<button class="btn google-btn">
							<i class="fab fa-google"></i> Google
						</button>
					</div>
					<div class="form-switch">
						<p>
							Don't have an account?
							<a href="#" id="show-register-mobile">Register Now</a>
						</p>
					</div>

					<ul class="benefits">
						<li>
							<i class="fas fa-shield-alt"></i> Secure and encrypted voting
						</li>
						<li>
							<i class="fas fa-check-circle"></i> Verify your vote was counted
						</li>
						<li>
							<i class="fas fa-mobile-alt"></i> Vote from anywhere, anytime
						</li>
					</ul>
				</div>

				<!-- Register Form Section -->
				<div class="form-section">
					<div class="glow glow-2"></div>
					<div class="form-title">
						<h2>Create Account</h2>
						<p>Join our democratic community</p>
					</div>
					<form id="registerForm">
						<div class="form-group">
							<i class="fas fa-user"></i>
							<input
								type="text"
								id="register-name"
								placeholder="Full Name"
								required />
						</div>
						<div class="form-group">
							<i class="fas fa-envelope"></i>
							<input
								type="email"
								id="register-email"
								placeholder="Email Address"
								required />
						</div>
						<div class="form-group">
							<i class="fas fa-lock"></i>
							<input
								type="password"
								id="register-password"
								placeholder="Password"
								required />
							<i
								class="fas fa-eye-slash password-toggle"
								id="register-password-toggle"></i>
							<div class="strength-meter"><div id="strength-bar"></div></div>
							<div class="strength-text" id="strength-text"></div>
						</div>
						<div class="form-group">
							<i class="fas fa-lock"></i>
							<input
								type="password"
								id="register-confirm-password"
								placeholder="Confirm Password"
								required />
						</div>
						<div class="form-group">
							<i class="fas fa-id-card"></i>
							<input
								type="text"
								id="register-voter-id"
								placeholder="Voter ID (Optional)" />
						</div>
						<div class="checkbox-group">
							<input type="checkbox" id="terms" required />
							<label for="terms"
								>I agree to the <a href="#">terms & conditions</a></label
							>
						</div>
						<button type="submit" class="btn">
							<i class="fas fa-user-plus"></i> Register
						</button>
					</form>
					<div class="form-switch">
						<p>
							Already have an account?
							<a href="#" id="show-login-mobile">Login</a>
						</p>
					</div>
				</div>
			</div>
		</div>

		<!-- Scripts -->
		<script src="https://cdnjs.cloudflare.com/ajax/libs/limonte-sweetalert2/11.7.5/sweetalert2.min.js"></script>
		<script>
			// Dark mode for SweetAlert
			const darkMode = {
				background: "#1e1e1e",
				color: "#e0e0e0",
			};

			// Password toggles
			const loginPasswordToggle = document.getElementById(
				"login-password-toggle"
			);
			const registerPasswordToggle = document.getElementById(
				"register-password-toggle"
			);
			const loginPassword = document.getElementById("login-password");
			const registerPassword = document.getElementById("register-password");

			loginPasswordToggle.addEventListener("click", () => {
				if (loginPassword.type === "password") {
					loginPassword.type = "text";
					loginPasswordToggle.classList.replace("fa-eye-slash", "fa-eye");
				} else {
					loginPassword.type = "password";
					loginPasswordToggle.classList.replace("fa-eye", "fa-eye-slash");
				}
			});

			registerPasswordToggle.addEventListener("click", () => {
				if (registerPassword.type === "password") {
					registerPassword.type = "text";
					registerPasswordToggle.classList.replace("fa-eye-slash", "fa-eye");
				} else {
					registerPassword.type = "password";
					registerPasswordToggle.classList.replace("fa-eye", "fa-eye-slash");
				}
			});

			// Password strength meter
			const strengthBar = document.getElementById("strength-bar");
			const strengthText = document.getElementById("strength-text");

			registerPassword.addEventListener("input", () => {
				const password = registerPassword.value;
				if (!password) {
					strengthBar.style.width = "0";
					strengthText.textContent = "";
					return;
				}

				// Calculate strength
				let strength = 0;
				if (password.length >= 8) strength += 25;
				if (/[A-Z]/.test(password)) strength += 25;
				if (/[0-9]/.test(password)) strength += 25;
				if (/[^A-Za-z0-9]/.test(password)) strength += 25;

				// Update UI
				strengthBar.style.width = `${strength}%`;

				if (strength <= 25) {
					strengthBar.style.backgroundColor = "#f87171";
					strengthText.textContent = "Weak";
					strengthText.style.color = "#f87171";
				} else if (strength <= 50) {
					strengthBar.style.backgroundColor = "#fbbf24";
					strengthText.textContent = "Fair";
					strengthText.style.color = "#fbbf24";
				} else if (strength <= 75) {
					strengthBar.style.backgroundColor = "#60a5fa";
					strengthText.textContent = "Good";
					strengthText.style.color = "#60a5fa";
				} else {
					strengthBar.style.backgroundColor = "#4ade80";
					strengthText.textContent = "Strong";
					strengthText.style.color = "#4ade80";
				}
			});

			// Mobile view form switching
			const showRegisterMobile = document.getElementById(
				"show-register-mobile"
			);
			const showLoginMobile = document.getElementById("show-login-mobile");
			const formSections = document.querySelectorAll(".form-section");

			if (showRegisterMobile && showLoginMobile) {
				showRegisterMobile.addEventListener("click", (e) => {
					e.preventDefault();
					formSections[0].style.display = "none";
					formSections[1].style.display = "block";
				});

				showLoginMobile.addEventListener("click", (e) => {
					e.preventDefault();
					formSections[1].style.display = "none";
					formSections[0].style.display = "block";
				});
			}

			// Check screen size on load and resize
			function checkScreenSize() {
				if (window.innerWidth <= 968) {
					formSections[1].style.display = "none";
				} else {
					formSections[0].style.display = "block";
					formSections[1].style.display = "block";
				}
			}

			window.addEventListener("load", checkScreenSize);
			window.addEventListener("resize", checkScreenSize);

			// Form submissions
			const loginForm = document.getElementById("loginForm");
			const registerForm = document.getElementById("registerForm");

			loginForm.addEventListener("submit", (e) => {
				e.preventDefault();
				const username = document.getElementById("login-username").value;
				const password = document.getElementById("login-password").value;

				// Here you would typically make an API call to your backend
				// This is a simulation for demo purposes

				// Simulate successful login
				Swal.fire({
					icon: "success",
					title: "Login Successful",
					text: "Welcome to the Voting System!",
					timer: 2000,
					showConfirmButton: false,
					background: darkMode.background,
					color: darkMode.color,
				}).then(() => {
					// Redirect to dashboard after successful login
					window.location.href =
						"https://v0-dark-theme-voters-page.vercel.app/";

					// For demo, we're just resetting the form
					loginForm.reset();
				});

				// Simulate failed login (uncomment to test)
				/*
            Swal.fire({
                icon: 'error',
                title: 'Login Failed',
                text: 'Invalid username or password. Please try again.',
                background: darkMode.background,
                color: darkMode.color
            });
            */
			});

			registerForm.addEventListener("submit", (e) => {
				e.preventDefault();
				const name = document.getElementById("register-name").value;
				const email = document.getElementById("register-email").value;
				const password = document.getElementById("register-password").value;
				const confirmPassword = document.getElementById(
					"register-confirm-password"
				).value;
				const voterId = document.getElementById("register-voter-id").value;

				// Validate passwords match
				if (password !== confirmPassword) {
					Swal.fire({
						icon: "error",
						title: "Registration Failed",
						text: "Passwords do not match. Please try again.",
						background: darkMode.background,
						color: darkMode.color,
					});
					return;
				}

				// Here you would typically make an API call to your backend
				// This is a simulation for demo purposes

				// Simulate successful registration
				Swal.fire({
					icon: "success",
					title: "Registration Successful",
					text: "Your account has been created! You can now login.",
					timer: 2000,
					showConfirmButton: false,
					background: darkMode.background,
					color: darkMode.color,
				}).then(() => {
					// For demo, we're just resetting the form
					registerForm.reset();
					strengthBar.style.width = "0";
					strengthText.textContent = "";

					// On mobile, switch to login form
					if (window.innerWidth <= 968) {
						formSections[1].style.display = "none";
						formSections[0].style.display = "block";
					}
				});
			});
		</script>
	</body>
</html>
