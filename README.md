# Ambulance-booking-system
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ambulance Booking System</title>
    <style>
        /* General Styles */
        body, html {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }

        /* Top Bar */
        .top-bar {
            background: #e8f0f5;
            padding: 10px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 14px;
            color: #333;
        }

        .top-bar a {
            text-decoration: none;
            color: #333;
            font-weight: bold;
        }

        /* Navbar */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 30px;
            background: #ffffff;
            box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            display: flex;
            align-items: center;
        }

        .logo img {
            width: 40px;
            margin-right: 10px;
        }

        .nav-links {
            list-style: none;
            display: flex;
            gap: 20px;
        }

        .nav-links li {
            display: inline;
        }

        .nav-links a {
            text-decoration: none;
            font-size: 16px;
            color: #333;
            padding: 10px;
        }

        .nav-links a:hover {
            color: red;
        }

        .book-btn {
            background: #27a79a;
            color: white;
            padding: 10px 15px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
        }

        .book-btn:hover {
            background: #1c7c6c;
        }

        /* Hero Section */
        .hero {
            position: relative;
            width: 100%;
            height: 80vh;
            background: url('https://img.freepik.com/premium-photo/emergency-ambulance-car-driving-with-flashing-red-lights-through-wide-city_1136105-53.jpg') no-repeat center center/cover;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: white;
        }

        .hero h1 {
            font-size: 36px;
            background: rgba(0, 0, 0, 0.5);
            padding: 15px 30px;
            border-radius: 5px;
        }

        .hero .read-more {
            background: #27a79a;
            padding: 12px 20px;
            text-decoration: none;
            color: white;
            font-weight: bold;
            border-radius: 5px;
            display: inline-block;
            margin-top: 20px;
        }

        .hero .read-more:hover {
            background: #1c7c6c;
        }

        /* Emergency Section */
        .emergency {
            background: #27a79a;
            text-align: center;
            color: white;
            padding: 50px 20px;
            margin-top: 20px;
        }

        .emergency h2 {
            font-size: 24px;
            margin-bottom: 20px;
        }

        .emergency-btn {
            background: white;
            color: #27a79a;
            padding: 12px 25px;
            border: 2px solid white;
            border-radius: 25px;
            text-decoration: none;
            font-size: 18px;
            font-weight: bold;
        }

        .emergency-btn:hover {
            background: rgba(255, 255, 255, 0.8);
            color: #1c7c6c;
        }

        /* About Us Section */
        .about-us {
            text-align: center;
            padding: 50px 20px;
            background: #f8f8f8;
        }

        .about-us h2 {
            font-size: 28px;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .about-us h3 {
            font-size: 20px;
            color: #27a79a;
            margin-bottom: 15px;
        }

        .about-us p {
            font-size: 16px;
            max-width: 800px;
            margin: auto;
            color: #555;
            line-height: 1.6;
        }
        /* Form Container */
        .form-container {
            max-width: 500px;
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
            margin: auto;
        }

        /* Form Title */
        .form-container h2 {
            color: #27a79a;
            margin-bottom: 20px;
        }

        /* Input Fields */
        .form-container input,
        .form-container select,
        .form-container textarea {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
            box-sizing: border-box;
        }

        /* Submit Button */
        .form-container button {
            background: #27a79a;
            color: white;
            padding: 15px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            width: 100%;
        }

        .form-container button:hover {
            background: #1c7c6c;
        }
        .microphone {
            margin-top: 20px;
            font-size: 16px;
            color: gray;
        }

        .active {
            color: red;
            font-weight: bold;
        }
        #ambulanceImages img {
            width: 150px;
            height: 100px;
            margin: 10px;
            border: 3px solid transparent;
            cursor: pointer;
        }
        .selected {
            border-color: red;
        }
        #details {
            display: none;
            margin-top: 20px;
            padding: 20px;
            border: 2px solid #ccc;
            text-align: left;
            width: 80%;
            margin: auto;
        }
        #confirmation-message {
            display: none;
            background: #d4edda;
            color: #155724;
            padding: 10px;
            margin-top: 10px;
            border: 1px solid #c3e6cb;
            border-radius: 5px;
            text-align: center;
        }
		#confirmation-tab {
            display: none;
            margin-top: 20px;
            padding: 20px;
            border: 2px solid #ccc;
            text-align: left;
            width: 80%;
            margin: auto;
        }

    </style>
</head>
<body>

    <div class="top-bar">
        <span>📧 Email: <a href="mailto:ambulance@gmail.com">ambulance@gmail.com</a></span>
        <span>📞 Call us now: +1234567890</span>
    </div>

    <div class="navbar">
        <div class="logo">
            <img src="https://cdn-icons-png.flaticon.com/512/2972/2972497.png" alt="Logo"> BNS
        </div>
        <ul class="nav-links">
            <li><a href="#">HOME</a></li>
            <li><a href="#">ABOUT</a></li>
            <li><a href="#">CONTACT</a></li>
            <li><a href="#" class="book-btn">Book an Ambulance</a></li>
        </ul>
    </div>

    <div class="hero">
        <div>
            <h1>Welcome to Ambulance Booking System</h1>
            <a href="#" class="read-more">Read More</a>
        </div>
    </div>

    <div class="emergency">
        <h2>In an emergency? Need help now?</h2>
        <a href="#" class="emergency-btn">Hire an Ambulance</a>
    </div>

    <div class="about-us">
        <h2>ABOUT US</h2>
        <h3>Emergency Ambulance Hiring Portal</h3>
        <p>
            We prioritize the well-being of our patients above all else. 
            That's why we offer top-notch ambulance services to ensure swift and secure medical transportation whenever the need arises. 
            Our dedicated team of skilled paramedics and drivers is equipped with state-of-the-art ambulances, 
            ready to respond to emergencies 24/7.
        </p>
    </div>
	<div class="form-container">
	<h2>HIRE AN AMBULANCE</h2>
        <form id="ambulance-form">
            <input type="text" placeholder="Enter Patient Name" required>
            <input type="text" placeholder="Enter Relative Name" required>
            <input type="tel" placeholder="Enter Relative Phone Number" required>
            <input type="text" placeholder="Enter Address" required>
            <input type="text" placeholder="Enter City" required>
            <input type="text" placeholder="Enter Province/State" required>
            
            <select required>
                <option value="">Select Type of Ambulance</option>
                <option>Basic Life Support</option>
                <option>Advanced Life Support</option>
                <option>Neonatal Ambulance</option>
            </select>
            
            <textarea placeholder="Message (Optional)"></textarea>
            
            <button type="submit">Submit</button>
        </form>
		<div id="confirmation-message">Booking Confirmed!</div>
    
        <p class="microphone">🎙 Voice Input: <span id="voiceStatus">Waiting...</span></p>
    </div>
	<div id="confirmation-tab">
        <h2>Booking Confirmation</h2>
        <p>Your booking details:</p>
        <div id="booking-details"></div>
    </div>

    <script>
        let recognition = new webkitSpeechRecognition();
        recognition.lang = "en-US";
        recognition.interimResults = false;
        recognition.maxAlternatives = 1;
        recognition.continuous = true;  // ✅ Keeps listening without stopping
        
        let fields = document.querySelectorAll("input, select, textarea");
        let currentIndex = 0;

        function speak(text) {
            let speech = new SpeechSynthesisUtterance(text);
            speech.lang = "en-US";
            speech.rate = 1.1;
            speech.pitch = 1;
            speechSynthesis.speak(speech);
        }

        window.onload = function() {
            if (!('webkitSpeechRecognition' in window)) {
                alert("Your browser does not support Speech Recognition. Please use Google Chrome.");
                return;
            }

            speak("Welcome to ambulance booking. Please fill in the details.");
            setTimeout(() => {
                speak("Please say your Patient Name.");
                recognition.start();
            }, 2000);
        };

        recognition.onresult = function(event) {
            let transcript = event.results[event.results.length - 1][0].transcript.trim();
            fields[currentIndex].value = transcript;
            
            document.getElementById("voiceStatus").innerText = "Captured: " + transcript;
            document.getElementById("voiceStatus").classList.remove("active");

            currentIndex++;
            if (currentIndex < fields.length) {
                let nextField = fields[currentIndex].placeholder || "Next field";
                setTimeout(() => speak("Please say: " + nextField), 500);
            } else {
                speak("All fields completed. Please submit the form.");
                recognition.stop();
            }
        };

        recognition.onerror = function(event) {
            document.getElementById("voiceStatus").innerText = "Error, retrying...";
            setTimeout(() => recognition.start(), 1000);
        };

		document.getElementById('ambulance-form').addEventListener('submit', function(event) {
            event.preventDefault(); // Prevent the form from submitting normally

            // Get form values
            const patientName = this.querySelector('input[placeholder="Enter Patient Name"]').value;
            const relativeName = this.querySelector('input[placeholder="Enter Relative Name"]').value;
            const relativePhone = this.querySelector('input[placeholder="Enter Relative Phone Number"]').value;
            const address = this.querySelector('input[placeholder="Enter Address"]').value;
            const city = this.querySelector('input[placeholder="Enter City"]').value;
            const provinceState = this.querySelector('input[placeholder="Enter Province/State"]').value;
            const ambulanceType = this.querySelector('select').value;
            const message = this.querySelector('textarea').value;

            // Display booking confirmation
            const bookingDetailsDiv = document.getElementById('booking-details');
            bookingDetailsDiv.innerHTML = `
                <p><strong>Patient Name:</strong> ${patientName}</p>
                <p><strong>Relative Name:</strong> ${relativeName}</p>
                <p><strong>Relative Phone Number:</strong> ${relativePhone}</p>
                <p><strong>Address:</strong> ${address}</p>
                <p><strong>City:</strong> ${city}</p>
                <p><strong>Province/State:</strong> ${provinceState}</p>
                <p><strong>Ambulance Type:</strong> ${ambulanceType}</p>
                <p><strong>Message:</strong> ${message}</p>
            `;

            document.getElementById('confirmation-tab').style.display = 'block';

            // Optionally, you can reset the form after displaying the confirmation
            this.reset();
        });
    </script>
	
	

</body>
</html>
