import RPi.GPIO as GPIO
import time
import requests
# Define GPIO pins for your sensors
flow_sensor_pin = 17
pressure_sensor_pin = 18
# Initialize GPIO
GPIO.setmode(GPIO.BCM)
GPIO.setup(flow_sensor_pin, GPIO.IN)
GPIO.setup(pressure_sensor_pin, GPIO.IN)
# URL of your platform to send data
platform_url = "https://your-iot-platform.com/api/data"
while True:
    # Read data from sensors
    flow_rate = GPIO.input(flow_sensor_pin)
    pressure = GPIO.input(pressure_sensor_pin)
    # Create a data payload
    data = {
        "flow_rate": flow_rate,
        "pressure": pressure,
        "timestamp": time.time()
    }
    # Send data to the platform
    response = requests.post(platform_url, json=data)
    # You can add error handling and other functionality here
    time.sleep(60)  # Adjust the time interval for data collection
