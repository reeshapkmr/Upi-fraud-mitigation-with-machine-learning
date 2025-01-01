## UPI Fraud Mitigation With Machine Learning

UPI Fraud Mitigation with Machine Learning is an innovative project aimed at safeguarding digital transactions in the growing Unified Payments Interface (UPI) ecosystem. With the increasing adoption of UPI, This project harnesses the power of machine learning to create a secure, intelligent system capable of detecting fraudulent transactions with high accuracy.  The project features a dynamic web interface for users to input transaction details and receive instant feedback, complemented by visual reports on transaction trends and fraud patterns.

### Project Structure:

```
upi-fraud-mitigation-with-machine-learning/
│
├── public/
│   ├── index1_intro-page.html         # Landing page introducing the project and its features.
│   ├── index2_login-page.html         # User login page to authenticate access to the system.
│   ├── index3_home-page.html          # Main user interface displaying system functionality and analytics.
│   ├── index4_entry-page.html         # Page for entering transaction details to check for fraud.
│   ├── index5_valid-page.html         # Confirmation page for transactions verified as legitimate.
│   ├── index6_invalid-page.html       # Warning page for transactions identified as fraudulent.
│   └── logincredentials_info.txt      # Sample login credentials for testing and demonstration purposes.
│
├── templates/
│   ├── index1.png(intro-page)         # Wireframe or screenshot of the introduction page.
│   ├── index2.png(login-page)         # Design template for the login page layout.
│   ├── index3.png(home-page)          # Image showing the design or layout of the dashboard.
│   ├── index4.png(entry-page)         # Visual guide for the data entry page structure.
│   ├── index5.png(valid-page)         # Image or mockup for the valid transaction confirmation view.
│   └── index6.png(invalid-page)       # Template for displaying the invalid transaction warning.
│
├── scripts/
│   ├── python.ipnyb                  # Jupyter Notebook for implementing fraud detection algorithms.
│   └── resultcheck.ipnyb             # Notebook for validating and visualizing the results of the fraud detection model.
│
├── data/
│   └── upitxnsdata.csv               # UPI transaction dataset for training, testing, and evaluating the ML model.
│
├── README.md                         # Comprehensive guide to understanding, setting up, and using the project.
├── .gitignore                        # Specifies files and directories to exclude from the repository.
└── LICENSE                           # Legal terms under which the project can be used, modified, or shared.               
```

### Screenshots:

***UPI Fraud Mitigation Intro-page***

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Intro.png)

***UPI Fraud Mitigation Login-page***

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Login.png)

***UPI Fraud Mitigation Home-page***

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Home.png)

***UPI Fraud Mitigation Entry-page***

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Entry.png)

***UPI Fraud Mitigation Valid-page***

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Valid.png)

***UPI Fraud Mitigation Invalid-page***

![image alt](https://github.com/reeshapkmr/Upi-fraud-mitigation-with-machine-learning/blob/bd635dc3a9bc7a37679bddc3943bae1ba6ed1a54/templates/UPI%20Fraud%20Mitigation%20Invalid.png)

***index1_intro-page.html***

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UPI Fraud Mitigation Intro</title>
    <style>
        body {
            margin: 0;
            overflow: hidden; /* Prevent scrolling */
            height: 100vh; /* Full height */
            display: flex;
            justify-content: center;
            align-items: center;
            background-image: url('../templates/index.png'); /* Replace with your image URL */
            background-size: cover; /* Cover the entire viewport */
            background-position: center; /* Center the image */
            opacity: 0; /* Start invisible */
            transition: opacity 0.5s ease; /* Fade-in and fade-out transition */
        }
        h1 {
            color: white; /* Text color */
            font-size: 3em; /* Font size */
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7); /* Text shadow for better visibility */
        }
    </style>
</head>
<body>
    <script>
        // Set the redirect URL
        const redirectUrl = 'index2_login-page.html'; // Replace with your next page URL

        // Fade in effect when the page loads
        window.onload = function() {
            document.body.style.opacity = 1; // Fade in the body
            setTimeout(() => {
                // Fade out effect before redirecting
                document.body.style.opacity = 0; // Start fade out
                setTimeout(() => {
                    window.location.href = redirectUrl; // Redirect after fade out
                }, 1000); // Wait for the fade-out transition to complete
            }, 500); // Display for 3 seconds before fading out
        };
    </script>
</body>
</html>
```

***index2_login-page.html***

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UPI Fraud Mitigation Login</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <style>
        body {
            background: url('../templates/index2.png') no-repeat center center fixed;
            background-size: cover;
            font-family: 'Arial', sans-serif;
        }

        /* Custom checkbox styles */
        .custom-checkbox {
            display: none; /* Hide the default checkbox */
        }

        .custom-label {
            display: flex;
            align-items: center;
            cursor: pointer;
        }

        .custom-label span {
            width: 16px; /* Reduced width */
            height: 16px; /* Reduced height */
            border: 1px solid white; /* White border initially */
            background-color: white; /* White background */
            display: inline-block;
            position: relative;
            margin-right: 8px;
            transition: border-color 0.3s, background-color 0.3s; /* Smooth transition */
        }

        .custom-checkbox:checked + .custom-label span {
            border-color: #FFD700; /* Golden border when checked */
            background-color: white; /* Keep background white when checked */
        }

        .custom-checkbox:checked + .custom-label span::after {
            content: '';
            position: absolute;
            left: 7px; /* Adjusted for smaller size */
            top: 2px; /* Adjusted for smaller size */
            width: 3px; /* Adjusted for smaller size */
            height: 10px; /* Adjusted for smaller size */
            border: solid #FFD700; /* Golden checkmark */
            border-width: 0 2px 2px 0;
            transform: rotate(45deg);
        }

        /* Input field styles */
        .input-field {
            border: 2px solid white; /* White border initially */
            transition: border-color 0.3s, color 0.3s; /* Smooth transition for border and text color */
            color: white; /* Default text color */
        }

        .input-field.valid {
            border-color: #FFD700; /* Golden border when valid */
            color: #FFD700; /* Change text color to golden when valid */
        }

        .form-text {
            color: white; /* Default text color for labels and other text */
            transition: color 0.3s; /* Smooth transition for text color */
        }

        .form-text.valid {
            color: #FFD700; /* Change text color to golden when valid */
        }

        .icon-golden {
            color: #FFD700; /* Golden color for icons */
        }
    </style>
    <script>
        function login(event) {
            event.preventDefault();
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            if (username === 'reeshapk' && password === 'reeshapk@1') {
                window.location.href = 'index3_home-page.html';
            } else {
                alert('Invalid username or password');
            }
        }

        function checkInputs() {
            const username = document.getElementById('username').value.trim();
            const password = document.getElementById('password').value.trim();
            const loginButton = document.getElementById('loginButton');
            const rememberMeCheckbox = document.getElementById('rememberMe');
            const formContainer = document.getElementById('formContainer');
            const formTextElements = document.querySelectorAll('.form-text');
            const usernameField = document.getElementById('username');
            const passwordField = document.getElementById('password');
            const usernameIcon = document.querySelector('.username-icon');
            const passwordIcon = document.querySelector('.password-icon');

            // Enable or disable the button based on input values
            if (username && password) {
                loginButton.disabled = false;
                loginButton.classList.remove('bg-gray-400', 'text-white', 'border-white', 'border-2');
                loginButton.classList.add('bg-white', 'text-yellow-500', 'border', 'border-yellow-500', 'border-2'); // Change to white background with golden text and border
                formContainer.classList.remove('border-white');
                formContainer.classList.add('border-yellow-500'); // Change form border to golden

                // Check if the credentials are correct and check the checkbox
                if (username === 'reeshapk' && password === 'reeshapk@1') {
                    rememberMeCheckbox.checked = true; // Automatically check the checkbox
                } else {
                    rememberMeCheckbox.checked = false; // Uncheck if credentials are incorrect
                }

                // Change input field borders and text color to golden
                usernameField.classList.add('valid');
                passwordField.classList.add('valid');
                usernameField.style.color = '#FFD700'; // Change input text color to golden
                passwordField.style.color = '#FFD700'; // Change input text color to golden
                formTextElements.forEach(element => element.classList.add('valid')); // Change all form text to golden

                // Change icon color to golden
                usernameIcon.classList.add('icon-golden');
                passwordIcon.classList.add('icon-golden');
            } else {
                loginButton.disabled = true;
                loginButton.classList.add('bg-gray-400', 'text-white', 'border', 'border-white', 'border-2'); // Set to gray with white text and border
                loginButton.classList.remove('bg-white', 'text-yellow-500', 'border-yellow-500'); // Remove golden styles
                formContainer.classList.add('border-white'); // Ensure form border is white
                formContainer.classList.remove('border-yellow-500'); // Remove golden border
                rememberMeCheckbox.checked = false; // Uncheck if fields are empty

                // Reset input field borders and text color to white
                usernameField.classList.remove('valid');
                passwordField.classList.remove('valid');
                usernameField.style.color = 'white'; // Reset text color to white
                passwordField.style.color = 'white'; // Reset text color to white
                formTextElements.forEach(element => element.classList.remove('valid')); // Reset all form text to white

                // Reset icon color
                usernameIcon.classList.remove('icon-golden');
                passwordIcon.classList.remove('icon-golden');
            }
        }
    </script>
</head>
<body class="flex items-center justify-center min-h-screen bg-black" style="font-family: 'Times New Roman', serif;">
    <div id="formContainer" class="bg-white bg-opacity-10 backdrop-blur-md rounded-lg p-8 w-96 border border-white border-2">
        <h2 class="text-2xl font-bold text-white text-center mb-6 form-text">Login</h2>
        <form onsubmit="login(event)">
            <div class="mb-4">
                <label class="block form-text mb-2" for="username">Username</label>
                <div class="relative">
                    <input class="w-full px-4 py-2 rounded-full bg-white bg-opacity-20 text-white placeholder-white focus:outline-none input-field" type="text" id="username" placeholder="Username" oninput="checkInputs()">
                    <i class="fas fa-user absolute right-3 top-3 text-white username-icon"></i>
                </div>
            </div>
            <div class="mb-4">
                <label class="block form-text mb-2" for="password">Password</label>
                <div class="relative">
                    <input class="w-full px-4 py-2 rounded-full bg-white bg-opacity-20 text-white placeholder-white focus:outline-none input-field" type="password" id="password" placeholder="Password" oninput="checkInputs()">
                    <i class="fas fa-lock absolute right-3 top-3 text-white password-icon"></i>
                </div>
            </div>
            <div class="flex items-center justify-between mb-6">
                <label class="flex items-center">
                    <input type="checkbox" id="rememberMe" class="custom-checkbox" />
                    <span class="custom-label">
                        <span></span>
                    </span>
                    <span class="text-white form-text">Remember me</span>
                </label>
                <a href="#" class="text-white form-text">Forgot password?</a>
            </div>
            <button id="loginButton" class="w-full py-2 rounded-full bg-gray-400 text-white font-bold border border-white border-2" disabled>Login</button>
        </form>
        <p class="text-center text-white mt-6 form-text">Don't have an account? <a href="#" class="font-bold">Register</a></p>
    </div>
</body>
</html>
```

***index3_home-page.html***

```
<html>
<head>
    <title>UPI Fraud Mitigation Home</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" rel="stylesheet" />
    <style>
        @keyframes shift {
            0% {
                transform: translateX(0);
            }
            100% {
                transform: translateX(calc(-100px * 18)); /* Adjust based on number of images and size */
            }
        }

        .scrolling-images {
            display: flex;
            overflow: hidden;
            width: 100%;
            white-space: nowrap;
        }

        .scrolling-wrapper {
            display: flex;
            animation: shift 35s steps(15) infinite; /* 18 steps for 18 images */
        }

        /* Optimized image scrolling for desktop */
.scrolling-images img {
    height: 100px; /* Adjust as needed */
    width: auto; /* This ensures the width scales based on the image aspect ratio */
    max-width: 100px; /* Ensures images don't get too large */
    margin-right: 2px;
    object-fit: contain;
}

/* Additional media query for larger desktop screens */
@media only screen and (min-width: 1200px) {
    .scrolling-images img {
        height: 120px; /* Increase size for larger screens */
        max-width: 120px;
    }
}

/* Additional media query for smaller devices (like tablets) */
@media only screen and (max-width: 768px) {
    .scrolling-images img {
        height: 80px; /* Reduce image size for smaller screens */
        max-width: 80px;
    }
}


        body {
    background-image: url('../templates/index3.png');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    background-attachment: fixed; /* Keep the background fixed even if the page scrolls */
    height: 100%;
    margin: 0;
    padding: 0;
}

    </style>
</head>
<body class="bg-black text-white">
    <header class="bg-black bg-opacity-45 text-white p-4 flex justify-between items-center">
        <div class="text-3xl font-bold" style="font-family: 'Times New Roman', Times, serif;">
            <span class="text-green-500">₹UPI</span> Fraud Mitigation With Machine Learning
        </div>
        <nav class="space-x-4">
            <a class="hover:underline" href="index4_entry-page.html" style="font-family: 'Times New Roman', Times, serif;">Platform</a>
            <a class="hover:underline" href="index4_entry-page.html" style="font-family: 'Times New Roman', Times, serif;">Amount</a>
            <a class="hover:underline" href="index4_entry-page.html" style="font-family: 'Times New Roman', Times, serif;">New Bal</a>
            <a class="hover:underline" href="index4_entry-page.html" style="font-family: 'Times New Roman', Times, serif;">Old Bal</a>
            <a class="hover:underline" href="index4_entry-page.html" style="font-family: 'Times New Roman', Times, serif;">DOB</a>
            <a class="hover:underline" href="index4_entry-page.html" style="font-family: 'Times New Roman', Times, serif;">DOT</a>
            <a class="hover:underline" href="index4_entry-page.html" style="font-family: 'Times New Roman', Times, serif;">TOT</a>
            <a class="hover:underline" href="index4_entry-page.html" style="font-family: 'Times New Roman', Times, serif;">PIN</a>
        </nav>
    </header>
    <section class="text-white p-4 overflow-hidden">
        <div class="scrolling-images">
            <div class="scrolling-wrapper">
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/s.png" /></a>
                <a href="index4_entry-page.html"><img alt="GPay" src="../templates/a.png" /></a>
                <a href="index4_entry-page.html"><img alt="Paytm" src="../templates/b.png" /></a>
                <a href="index4_entry-page.html"><img alt="Phonepe" src="../templates/c.png" /></a>
                <a href="index4_entry-page.html"><img alt="BHIM" src="../templates/d.png" /></a>
                <a href="index4_entry-page.html"><img alt="AmazonPay" src="../templates/e.png" /></a>
                <a href="index4_entry-page.html"><img alt="MobiKwik" src="../templates/f.png" /></a>
                <a href="index4_entry-page.html"><img alt="WhatsappPay" src="../templates/g.png" /></a>
                <a href="index4_entry-page.html"><img alt="BharatPay" src="../templates/h.png" /></a>
                <a href="index4_entry-page.html"><img alt="JioPay" src="../templates/i.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/j.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/k.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/l.png" /></a>
                <a href="index4_entry-page.html"><img alt="PayZapp" src="../templates/m.png" /></a>
                <a href="index4_entry-page.html"><img alt="IPay" src="../templates/n.png" /></a>
                <a href="index4_entry-page.html"><img alt="YonoSBI" src="../templates/o.png" /></a>
                <a href="index4_entry-page.html"><img alt="AxisPay" src="../templates/p.png" /></a>
            </div>
        </div>
    </section>

    <section class="text-white p-4 flex flex-wrap justify-center space-x-4 space-y-4">
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                GooglePay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                PhonePe
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                BHIM
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                Paytm
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                AmazonPay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                MobiKwik
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                WhatsappPay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                BharatPay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                JioPay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                IPay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                YonoSBI
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                AxisPay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                PayZapp
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                Kotak811
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                FreeCharge
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                ICICI
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                Cred
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                GooglePay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                PhonePe
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                BHIM
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                Paytm
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                AmazonPay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                MobiKwik
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                WhatsappPay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                BharatPay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                JioPay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                IPay
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                YonoSBI
            </button>
        </a>
        <a href="index4_entry-page.html">
            <button class="bg-gray-800 bg-opacity-75 text-gold px-4 py-2 rounded" style="font-family: 'Times New Roman', Times, serif; color: #FFD700; border: 1.5px solid #FFD700;">
                AxisPay
            </button>
        </a>
    </section>
</body>
</html>
```

***index4_entry-page.html***

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UPI Fraud Mitigation Entry</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <style>
        body {
            background: url('../templates/index4.png') no-repeat center center fixed;
            background-size: cover;
            font-family: 'Times New Roman', serif;
        }

        /* Form container styles */
        #formContainer {
            border: 2px solid white; /* White border initially */
            transition: border-color 0.3s; /* Smooth transition for border color */
        }

        /* Input field styles */
        .input-field {
            border: 2px solid white; /* White border initially */
            transition: border-color 0.3s, color 0.3s; /* Smooth transition for border and text color */
            color: white; /* Default text color */
        }

        .input-field.valid {
            border-color: #FFD700; /* Golden border when valid */
            color: #FFD700; /* Change text color to golden when valid */
        }

        .form-text {
            color: white; /* Default text color for labels and other text */
            transition: color 0.3s; /* Smooth transition for text color */
        }

        .form-text.valid {
            color: #FFD700; /* Change text color to golden when valid */
        }

        .icon-golden {
            color: #FFD700; /* Golden color for icons */
        }

        #submitBtn {
            background-color: gray; /* Default gray background */
            color: white; /* Default white text */
            cursor: not-allowed; /* Default cursor */
            border: 2px solid white; /* White border initially */
            transition: border-color 0.3s; /* Smooth transition for border color */
        }

        #submitBtn.valid {
            background-color: white; /* Change to white background when valid */
            color: #FFD700; /* Change text color to golden when valid */
            cursor: pointer; /* Change cursor to pointer when valid */
            border-color: #FFD700; /* Change border color to golden when valid */
        }

        #formContainer.valid {
            border-color: #FFD700; /* Change form border color to golden when valid */
        }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen bg-black">
    <div id="formContainer" class="bg-white bg-opacity-10 backdrop-blur-md rounded-lg p-2 w-96">
        <h2 class="text-2xl font-bold text-white text-center mb-6 form-text">Transaction Details</h2>
        <form id="transactionForm">
            <!-- Recipient Name -->
            <div class="mb-4">
                <label class="block mb-2 form-text" for="recipient">Recipient Name</label>
                <div class="relative">
                    <input id="recipient" class="w-full px-4 py-2 rounded-full bg-white bg-opacity-20 text-white placeholder-white focus:outline-none input-field" type="text" 
                           placeholder="Enter Recipient Name">
                    <i class="fas fa-user-check absolute right-3 top-3 text-white"></i>
                </div>
            </div>
            <!-- Transaction ID -->
            <div class="mb-4">
                <label class="block mb-2 form-text" for="transactionId">Transaction ID</label>
                <div class="relative">
                    <input id="transactionId" class="w-full px-4 py-2 rounded-full bg-white bg-opacity-20 text-white placeholder-white focus:outline-none input-field" type="text" 
                         placeholder="Enter Transaction ID">
                    <i class="fas fa-id-card absolute right-3 top-3 text-white"></i>
                </div>
            </div>
            <!-- Amount -->
            <div class="mb-4">
                <label class="block mb-2 form-text" for="amount">Amount</label>
                <div class="relative">
                    <input id="amount" class="w-full px-4 py-2 rounded-full bg-white bg-opacity-20 text-white placeholder-white focus:outline-none input-field" type="number" 
                              placeholder="Enter Amount">
                    <i class="fas fa-dollar-sign absolute right-3 top-3 text-white"></i </div>
            </div>
            <!-- Old Balance -->
            <div class="mb-4">
                <label class="block mb-2 form-text" for="oldBalance">Old Balance</label>
                <div class="relative">
                    <input id="oldBalance" class="w-full px-4 py-2 rounded-full bg-white bg-opacity-20 text-white placeholder-white focus:outline-none input-field" type="number" 
                           placeholder="Enter Old Balance">
                    <i class="fas fa-dollar-sign absolute right-3 top-3 text-white"></i>
                </div>
            </div>
            <!-- New Balance -->
            <div class="mb-4">
                <label class="block mb-2 form-text" for="newBalance">New Balance</label>
                <div class="relative">
                    <input id="newBalance" class="w-full px-4 py-2 rounded-full bg-white bg-opacity-20 text-white placeholder-white focus:outline-none input-field" type="number" 
                           placeholder="Enter New Balance">
                    <i class="fas fa-dollar-sign absolute right-3 top-3 text-white"></i>
                </div>
            </div>
            <!-- Platform -->
            <div class="mb-4">
                <label class="block mb-2 form-text" for="platform">Platform</label>
                <div class="relative">
                    <input id="platform" class="w-full px-4 py-2 rounded-full bg-white bg-opacity-20 text-white placeholder-white focus:outline-none input-field" type="text" 
                            placeholder="Enter Platform">
                    <i class="fas fa-user absolute right-3 top-3 text-white"></i>
                </div>
            </div>
            <button id="submitBtn" type="submit" class="w-full py-2 rounded-full bg-gray-500 text-gray-300 font-bold cursor-not-allowed" disabled>Submit</button>
        </form>
    </div>

    <script>
        const inputs = document.querySelectorAll("#transactionForm input");
        const submitBtn = document.getElementById("submitBtn");
        const formContainer = document.getElementById("formContainer");
        const formTexts = document.querySelectorAll('.form-text');

        // Function to check if all inputs are filled
        function checkInputs() {
            let allFilled = true;
            inputs.forEach(input => {
                if (input.value.trim() === "") {
                    allFilled = false;
                    input.classList.remove('valid');
                } else {
                    input.classList.add('valid');
                }
            });
            // Only apply the valid class if all required fields are filled
            if (allFilled) {
                inputs.forEach(input => input.classList.add('valid'));
                formContainer.classList.add('valid'); // Add valid class to form container
                formTexts.forEach(text => text.classList.add('valid')); // Change text color to golden
            } else {
                inputs.forEach(input => input.classList.remove('valid'));
                formContainer.classList.remove('valid'); // Remove valid class from form container
                formTexts.forEach(text => text.classList.remove('valid')); // Reset text color
            }
            submitBtn.disabled = !allFilled; // Enable or disable the button
            submitBtn.classList.toggle("valid", allFilled);
        }

        // Add event listener to all inputs
        inputs.forEach(input => {
            input.addEventListener("input", checkInputs);
        });

        // Initial check
        checkInputs();

        document.getElementById('transactionForm').addEventListener('submit', function(event) {
            event.preventDefault(); // Prevent the default form submission

            // Get input values
            const recipient = document.getElementById('recipient').value.trim();
            const transactionId = document.getElementById('transactionId').value.trim();
            const amount = parseFloat(document.getElementById('amount').value);
            const oldBalance = parseFloat(document.getElementById('oldBalance').value);
            const newBalance = parseFloat(document.getElementById('newBalance').value);
            const platform = document.getElementById('platform').value.trim();
            {
                window.location.href = 'index6_invalid-page.html';
            }
        });
    </script>
</body>
</html>
```

***index5_valid-page.html***

```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UPI Fraud Mitigation Valid</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <style>
        body {
            background: url('../templates/index5.png') no-repeat center center fixed;
            background-size: cover;
            font-family: 'Times New Roman', serif; /* Changed to Times New Roman */
        }
        .text-green-500 {
            color: #FFD700; /* Gold color */
        }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen bg-black">
    <div class="bg-white bg-opacity-10 backdrop-blur-md rounded-lg p-20 w-102 border-2 border-yellow-500"> <!-- Added golden border to the form -->
        <h2 class="text-4xl font-bold text-center mb-6" 
        style="
        color: #04e758; /* Green-500 */
        text-shadow: 
       -1px -1px 0 #f59e0b,  /* Yellow-500 shadow for top-left */
        1px -1px 0 #f59e0b,   /* Yellow-500 shadow for top-right */
       -1px 1px 0 #f59e0b,   /* Yellow-500 shadow for bottom-left */
        1px 1px 0 #f59e0b,    /* Yellow-500 shadow for bottom-right */
        0 -1px 0 #f59e0b,     /* Yellow-500 shadow for top */
        0 1px 0 #f59e0b,      /* Yellow-500 shadow for bottom */
       -1px 0 0 #f59e0b,     /* Yellow-500 shadow for left */
        1px 0 0 #f59e0b;      /* Yellow-500 shadow for right */">Valid Transaction! (Legitimate)</h2>
        <p class="text-2xl text-yellow-500">Your transaction has been processed successfully.</p>
        <div class="mt-4">
            <h2 class="text-2xl text-center text-yellow-500 font-semibold">Transaction Details:</h2>
            <h2 class="text-yellow-500 font-semibold">.......................................................................................................................</h2>
            <p class="text-1xl text-center text-yellow-500"><strong>Recipient:</strong> <span id="recipientDisplay"></span></p>
            <p class="text-1xl text-center text-yellow-500"><strong>TransactionId:</strong> <span id="transactionIdDisplay"></span></p>
            <p class="text-1xl text-center text-yellow-500"><strong>Amount:</strong> <span id="amountDisplay"></span></p>
            <p class="text-1xl text-center text-yellow-500"><strong>Old Balance:</strong> <span id="oldBalanceDisplay"></span></p>
            <p class="text-1xl text-center text-yellow-500"><strong>New Balance:</strong> <span id="newBalanceDisplay"></span></p>
            <p class="text-1xl text-center text-yellow-500"><strong>Platform:</strong> <span id="platformDisplay"></span></p>
            <h2 class="text-yellow-500 font-semibold">.......................................................................................................................</h2>
        </div>
        <div class="flex justify-center mt-6">
            <a href="index4_entry-page.html" class="inline-block px-9 py-2 bg-white text-yellow-500 border-2 border-yellow-500 rounded-full hover:bg-gray-200">Go Back</a> <!-- Updated button styles -->
        </div>
    </div>    
    <script>
        // Get the URL parameters
        const urlParams = new URLSearchParams(window.location.search);
        const recipient = urlParams.get('recipient');
        const transactionId = urlParams.get('transactionId');
        const amount = urlParams.get('amount');
        const oldBalance = urlParams.get('oldBalance');
        const newBalance = urlParams.get('newBalance');
        const platform = urlParams.get('platform');

        // Display the transaction details
        document.getElementById('recipientDisplay').textContent = recipient;
        document.getElementById('transactionIdDisplay').textContent = transactionId;
        document.getElementById('amountDisplay').textContent = `₹${amount}`;
        document.getElementById('oldBalanceDisplay').textContent = `₹${oldBalance}`;
        document.getElementById('newBalanceDisplay').textContent = `₹${newBalance}`;
        document.getElementById('platformDisplay').textContent = platform;
    </script>
</body>
</html>
```

***index6_invalid-page.html***

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UPI Fraud Mitigation Invalid</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <style>
        body {
            background: url('../templates/index5.png') no-repeat center center fixed;
            background-size: cover;
            font-family: 'Times New Roman', serif; /* Changed to Times New Roman */
        }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen bg-black">
    <div class="bg-white bg-opacity-10 backdrop-blur-md rounded-lg p-20 w-102 border-2 border-yellow-500"> <!-- Added border classes -->
        <h2 class="text-4xl font-bold text-center mb-6"
        style="
        color: red;
        text-shadow: 
       -1px -1px 0 #f59e0b,
        1px -1px 0 #f59e0b,
       -1px 1px 0 #f59e0b,
        1px 1px 0 #f59e0b;">Invalid Transaction! (Fraudulent)</h2>
        <p class="text-2xl text-yellow-500">Unfortunately, your transaction could not be processed.</p>
        <div class="mt-4">
            <h2 class="text-2xl text-center text-yellow-500 font-semibold">Transaction Details:</h2>
            <h2 class="text-yellow-500 font-semibold">.......................................................................................................................</h2>
            <p class="text-1xl text-center text-yellow-500"><strong>Please check the details and try again.</strong></p> <!-- Changed to red -->
            <h2 class="text-yellow-500 font-semibold">.......................................................................................................................</h2>
        </div>
        <div class="flex justify-center mt-6">
            <a href="index4_entry-page.html" class="inline-block px-9 py-2 bg-white text-yellow-500 border-2 border-yellow-500 rounded-full hover:bg-gray-200">Go Back</a>
        </div>
    </div>
</body>
</html>
```
