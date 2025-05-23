# Precision-Li-iivestock-Farming-
Precision Livestock Farming System

Code 1: Livestock Health Monitoring



import random

import time



# Simulated sensor data for a group of animals

livestock_data = [

    {"id": "Cow 001", "temperature": 38.5, "activity": 70, "heart_rate": 65},

    {"id": "Cow 002", "temperature": 39.2, "activity": 30, "heart_rate": 80},

    {"id": "Cow 003", "temperature": 40.1, "activity": 20, "heart_rate": 95},  # abnormal

    {"id": "Cow 004", "temperature": 37.8, "activity": 85, "heart_rate": 60}

]



# Thresholds for abnormal health

TEMP_THRESHOLD = 39.5

ACTIVITY_THRESHOLD = 25

HEART_RATE_THRESHOLD = 90



# Function to analyze data

def analyze_livestock(data):

    alerts = []

    for animal in data:

        abnormal = []

        if animal["temperature"] > TEMP_THRESHOLD:

            abnormal.append("High Temp")

        if animal["activity"] < ACTIVITY_THRESHOLD:

            abnormal.append("Low Activity")

        if animal["heart_rate"] > HEART_RATE_THRESHOLD:

            abnormal.append("High Heart Rate")

        if abnormal:

            alerts.append({

                "id": animal["id"],

                "issues": abnormal,

                "status": "Alert"

            })

        else:

            alerts.append({

                "id": animal["id"],

                "issues": ["Normal"],

                "status": "OK"

            })

    return alerts



# Display results

def display_dashboard(results):

    print("=== Precision Livestock Monitoring Dashboard ===\n")

    for result in results:

        print(f"Animal ID : {result['id']}")

        print(f"Status    : {result['status']}")

        print(f"Issues    : {', '.join(result['issues'])}")

        print("----------------------------------------------")



# Simulate a reading every few seconds

if __name__ == "__main__":

    print("Starting Livestock Health Monitoring...\n")

    time.sleep(1)

    analysis = analyze_livestock(livestock_data)

    display_dashboard(analysis)



Code 2: Real-time Sensor Monitoring and Alerts



import time

import random

import matplotlib.pyplot as plt



# Simulated sensor reading function

def read_sensors():

    temperature = random.uniform(20.0, 35.0)  # Ambient temp (simulated)

    humidity = random.uniform(20.0, 60.0)     # Humidity (simulated)

    animal_temp = random.uniform(36.5, 40.0)  # Animal body temp (simulated)

    return temperature, humidity, animal_temp



# Function to send alerts

def send_alert(message):

    print(f'ALERT: {message}')



# Initialize data lists

temperature_data = []

humidity_data = []

animal_temp_data = []



# Real-time monitoring loop (simulated)

run = True

while run:

    temperature, humidity, animal_temp = read_sensors()



    temperature_data.append(temperature)

    humidity_data.append(humidity)

    animal_temp_data.append(animal_temp)



    if temperature > 30:

        send_alert('High ambient temperature detected!')

    if humidity < 30:

        send_alert('Low humidity detected!')

    if animal_temp >= 39:

        send_alert('High animal temperature detected!')



    # Plotting real-time data

    plt.clf()

    plt.plot(temperature_data, label='Ambient Temperature')

    plt.plot(humidity_data, label='Humidity')

    plt.plot(animal_temp_data, label='Animal Temperature')

    plt.legend()

    plt.pause(1)



    if len(temperature_data) > 50:

        run = False  # Stop after 50 readings (for simulation)



Code 3: Same as Code 2 (Repeated for clarity)



import time

import random

import matplotlib.pyplot as plt



# Simulated sensor reading function

def read_sensors():

    temperature = random.uniform(20.0, 35.0)  # Ambient temp (simulated)

    humidity = random.uniform(20.0, 60.0)     # Humidity (simulated)

    animal_temp = random.uniform(36.5, 40.0)  # Animal body temp (simulated)

    return temperature, humidity, animal_temp



# Function to send alerts

def send_alert(message):

    print(f'ALERT: {message}')



# Initialize data lists

temperature_data = []

humidity_data = []

animal_temp_data = []



# Real-time monitoring loop (simulated)

run = True

while run:

    temperature, humidity, animal_temp = read_sensors()



    temperature_data.append(temperature)

    humidity_data.append(humidity)

    animal_temp_data.append(animal_temp)



    if temperature > 30:

        send_alert('High ambient temperature detected!')

    if humidity < 30:

        send_alert('Low humidity detected!')

    if animal_temp >= 39:

        send_alert('High animal temperature detected!')



    # Plotting real-time data

    plt.clf()

    plt.plot(temperature_data, label='Ambient Temperature')

    plt.plot(humidity_data, label='Humidity')

    plt.plot(animal_temp_data, label='Animal Temperature')

    plt.legend()

    plt.pause(1)



    if len(temperature_data) > 50:

        run = False  # Stop after 50 readings (for simulation)

