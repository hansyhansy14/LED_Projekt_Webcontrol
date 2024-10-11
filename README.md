Flask LED Control Application
This project is a web-based application built with Flask that allows users to control an LED connected to a Raspberry Pi. The application provides a simple web interface where users can turn the LED on and off, and it displays the time when the LED was last turned on.

Features
Web-based control for turning an LED on and off.
Displays the time when the LED was last turned on.
Built using Flask, a lightweight web framework for Python.
Uses GPIO (General Purpose Input/Output) pins of the Raspberry Pi to control the LED.
Prerequisites
Hardware:

Raspberry Pi with Raspbian OS installed.
An LED connected to the GPIO pin 17 on the Raspberry Pi (with a resistor).
Software:

Python 3.x installed on the Raspberry Pi.
Flask web framework.
RPi.GPIO Python module for interacting with the GPIO pins.
Installation and Setup
Clone the repository (or copy the code to your Raspberry Pi):

bash
Copy code
git clone https://github.com/your-repo/flask-led-control.git
cd flask-led-control
Install necessary dependencies:

Install Flask and the RPi.GPIO library by running the following commands:

bash
Copy code
sudo apt-get install python3-flask
sudo apt-get install python3-rpi.gpio
Connect the LED:

Connect the positive leg (longer leg) of the LED to GPIO pin 17 (BCM mode).
Connect the negative leg (shorter leg) to a 330Ω resistor, then connect the resistor to the ground pin (GND).
Running the Application
Start the Flask server:

Run the following command to start the application:

bash
Copy code
python3 app.py
Access the web interface:

Open a web browser on the Raspberry Pi or another device on the same network.
Enter the following URL: http://<raspberry-pi-ip-address>:5000/.
Replace <raspberry-pi-ip-address> with your Raspberry Pi's actual IP address.
You should see a simple web page that allows you to turn the LED on and off.
Code Explanation
app.py: The main file for the Flask application. It defines two routes:
/: Displays the main page.
/set_led: Handles the POST request when the user turns the LED on or off.
Key Functions:
index(): Renders the HTML page without any initial message.
control_led(): Receives the LED status (on/off) from the web form, updates the GPIO pins to turn the LED on or off, and returns a message indicating the status of the LED.
GPIO Pin Configuration
The application uses GPIO pin 17 (BCM mode) to control the LED. If you'd like to use a different GPIO pin, update the led variable in the code:

python
Copy code
led = 17  # Change this to your preferred GPIO pin number
Troubleshooting
LED not turning on/off:
Check that the LED is connected properly to the Raspberry Pi GPIO pins.
Verify the GPIO pin number in the code matches the pin where the LED is connected.
App not accessible via the browser:
Ensure your Raspberry Pi and the device accessing the app are on the same network.
Use ifconfig or hostname -I to get the IP address of the Raspberry Pi.
License
This project is licensed under the MIT License. Feel free to use and modify it as needed.
