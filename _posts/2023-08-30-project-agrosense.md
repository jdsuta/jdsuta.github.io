---
layout: post
title:  "AgroSense"
author: david
categories: [ Projects ]
image: assets/images/agrosense-plan.jpeg
tags: [projects, iot, flask ]
comments: true
---

AgroSense was my final project for [CS50x Harvard's][cs50x-harvard]{:target="_blank"} course. It is an IoT application that collects and monitors data from plants using an Arduino-based board (Intel Galileo), transmitting it to a web app for processing. The aim is to improve plant care and management by delivering real-time data and alerts.

### Agrosense in Action

Discover the capabilities of Agrosense through this engaging video presentation. Dive into the world of Agrosense and witness its features in action. 

<p>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/QdPggtvKLwg" frameborder="0" allowfullscreen></iframe>
</p>


### Main Technology Stack:

- **Back End (BE):** Python with Flask, Sendgrid API for email communication.
- **Front End (FE):** HTML, JavaScript, Bootstrap.
- **Device:** Intel Galileo, an Arduino-certified development board based on Intel x86 architecture. It's programmed using the Arduino interface to collect and transmit data to the web server.

The concept for AgroSense came from my personal experience. Witnessing my father's passion for plants and his frequent travels, inspired me to create a solution that enables him to remotely monitor his plants' condition and receive timely notifications.

Using AgroSense involves registering on the web app, generating a unique device name, and an API key for identification. Users connect the Intel Galileo board to their plants through sensors that capture temperature, moisture, and time data. The board sends this information as a **POST request** to the web server every 5 minutes (this timeframe is adjustable).

The web app showcases a summary of the last 7 days, presenting average temperature and humidity in a table format. It generates graphs illustrating temperature and humidity fluctuations over time for each device. Users can access and review this data by logging into the web app.

One of the key features of AgroSense is the alarm email function. If the recorded temperature or humidity falls outside a predefined range, an alert email is automatically sent to the email address associated with the device. This way, users can take immediate action to prevent potential harm to the plants.

AgroSense also empowers users to create and send data to the web server via **API**. This flexibility serves for testing purposes and facilitates integration with other applications.

The main outcomes and results of AgroSense include:

- Convenient and reliable remote monitoring of plant health and growth.
- Optimization of plant care and early problem prevention through real-time data and alerts.
- Showcasing the potential of IoT technology for creating smart solutions for everyday problems.

For a detailed description of its functionality and the project's development, visit the [Github - Agrosense's][github-agrosense]{:target="_blank"} section.

[cs50x-harvard]: https://cs50.harvard.edu/x/2023/
[github-agrosense]: https://github.com/jdsuta/Agrosense/blob/main/README.md 


<p style="font-size: 16px;">
 <strong>Credits:</strong><a href="https://www.freepik.com/free-photo/close-up-woman-examining-plant-growth-using-touchpad-while-working-plant-nursery_25623989.htm#query=smart%20plant&position=17&from_view=search&track=ais" target="_blank">
    Blog's image by Drazen Zigic
  </a>
</p>