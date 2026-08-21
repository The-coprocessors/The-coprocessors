# Hello! We are **Team Coprocessors**.

<img src="./docs/team photo.jpeg" alt="Team Photo" width=600>

# WRO 2026 - Future Innovators - Robotics Project Documentation

## Team Members

- **Sarah Stacie Solomon**
- **Parmita V**

We are a team of students passionate about robotics, AI, and culture. Nexus 2.0 combines technology with cultural preservation to collect, protect, and share stories and knowledge. This repository documents our robot’s design, components, coding, AI, development, and testing.

## Table of Contents 

- [1.Overview](#1-overview)
   - [1.1 About the Project](#11-about-the-project)
   - [1.2 Bot Images](#12-Bot-Images)
- [2.Mobility Management](#2-Mobility-Managemennt)
   - [2.1 Driver System](#21-Driver-System)
   - [2.2 Steering](#22-Steering)
   - [2.3 Chassis Design](#23-Chassis-Design)
- [3.Power and Sence Management](#3-Power-and-Sence-Mannagement)
   - [3.1 Power Source](#31-Power-Source)
   - [3.2 Sensors and Camera](#32-Sensors-and-camera)
   - [3.3 Processing Units](#33-Processing-Units)
   - [3.4 Circuit Diagram](#34-Circuit-Diagram)
   - [3.5 Power Consuption](#35-Power-Consumption)
- [4.Source Code](#4-Source-Code)
   - [4.1 API Documents](#41-API-documents)
   - [4.2 Code Structure](#42-Code-Structure)
   - [4.3 Complitation/Upload Instructions](#43-complitation-/-Upload-Structure)
- [5.List of components](#5-Source-Code)
   - [5.1 Nexus](#51-Nexus)
   - [5.2 Nexus Nano](#52-Nexus-Nano)
- [6.Edge Intellegence](#6-Edge-Intellegence)
- [7.3D Model](#7-3D-Model)
   - [7.1 Images](#71-Images)
   - [7.2 STL Files](#72-STL-Files)
- [8.Source code](#8-Source-code)
- [9.Building Challanges](#9-Building-Challanges)
- [10.Extras](#10-Extras)

 
## 1.Overview

### 1.1 About the Project

Nexus 2.0 is an AI-powered cultural storytelling and assistance robot designed to make India's cultural heritage more interactive, accessible, and engaging.

Nexus acts as a “Guardian of Stories”, combining artificial intelligence, robotics, computer vision, voice interaction, and autonomous mobility to interact with visitors and help them explore cultural knowledge.
At the heart of Nexus is the idea that cultural heritage is not limited to monuments, artefacts, or written records. People themselves carry stories, memories, traditions, and knowledge. Nexus is designed to help bring these stories to life through natural interaction.

Nexus is connected to our broader Echoes ecosystem, where authentic stories and cultural knowledge can be collected, processed, preserved, and eventually shared through interactive platforms.

The robot uses an NVIDIA Jetson Nano as its primary computing unit and integrates technologies such as YOLOv8 for computer vision, speech processing, a touchscreen interface, and a Mecanum-wheel mobility system.

Our goal is to create a system where technology does not replace the human connection to culture, but instead helps more people discover, understand, and remember the stories behind it.

### 1.2 Bot Images

This section showcases the physical development of Nexus 2.0, from its overall design to the completed prototype.
The images below document the robot's mechanical structure, electronic integration, display system, mobility system, and final appearance.


## 2.Mobility Management

### 2.1 Drive System

Nexus 2.0 uses a four-wheel Mecanum drive system to achieve flexible and precise movement in indoor environments.
Each Mecanum wheel is independently driven by a motor. The angled rollers on the wheels allow the robot to generate movement in multiple directions by controlling the speed and direction of individual wheels.

The drive system enables Nexus to:

Move forward and backward
Strafe left and right
Move diagonally
Rotate in place
Perform controlled combinations of these movements

The motor controller receives movement commands from the robot's control system and converts them into individual motor movements.

This mobility system is particularly useful for Nexus because cultural spaces such as museums and exhibitions may have limited space and frequent pedestrian movement. The ability to move sideways and rotate without large turning circles allows Nexus to manoeuvre more.

Specifications:
Drive Type: 4-wheel Mecanum drive
Number of Wheels: 4
Wheel Type: Mecanum
Motor Type: [Motor model]
Motor Driver: L298N
Motor Voltage: [Voltage]
Motor Torque: Torque
Wheel Diameter: Diameter
Control Unit: Audrino UNO
Processing Unit: NVIDIA Jetson Nano

### 2.2 Steering

- YOLO-Based Steering and Obstacle Avoidance

Nexus 2.0 uses YOLOv8-based computer vision to detect objects in its path and assist with steering decisions. A camera captures the environment and sends the visual data to the NVIDIA Jetson Nano, where YOLOv8 identifies objects and determines their position within the camera's field of view.

The detected information is then used to decide whether Nexus should continue in its current direction or adjust its movement to avoid an obstacle.

 - Specifications:

Object Detection Model: YOLOv8
Processing Unit: NVIDIA Jetson Nano
Camera: 720p camera
Steering Method: Vision-assisted steering
Drive System: 4-wheel Mecanum drive
Motor Driver: L298N
Microcontroller: Arduino UNO R3. 

### 2.3 Chassis Design

- Chassis Overview

<table>
  <tr>
    <td align="center">
      <b>Side View</b><br>
      <img src="./docs/chassis 1.jpeg" alt="chassis 1.1" width=400>
    </td>
    <td align="center">
      <b>Top View</b><br>
      <img src="./docs/chassis 2.jpeg" alt="chassis 1.2" width=400>
    </td>


| Dimension   | Value (mm)  |
| ----------- | ----------- |
| Width       | 244         |
| Length      | 120         |
| Height      | 59          |

- Design Overview

Our chassis was designed with a focus on stability, weight distribution, and modularity. The goal was to create a stable platform for the Mecanum drive system while keeping the major components centred and securely mounted. 
The modular design also allows individual components to be easily accessed, replaced, or upgraded during development.

-  Layout

The layout of the Nexus 2.0 chassis is designed to accommodate the four Mecanum wheels and their motors, while keeping the battery, electronics, and computing components securely positioned within the body. The camera and display are placed to provide clear interaction with the surroundings and users, while the central placement of electronics helps simplify wiring and maintain balanced weight distribution.

The chassis was custom-designed in FreeCAD and [3D printed/fabricated using [MATERIAL]]. The design was refined through multiple iterations to achieve proper component alignment and stability. Separate mounts and brackets are used for components such as the motors, camera, display, and sensors. The chassis is also designed with modularity in mind, allowing individual components to be replaced or upgraded without redesigning the entire structure.


## 3.Power and sense management 

### 3.1 Power Source

**Battery: lithium ion 16046**

<table>
  <tr>
    <td align="center" width="300" >
      <img src="./docs/Lithium ion.jpeg" alt="Lithium Ion Battery" width = 100% >
    </td>
    <td>
      <h3>Specifications:</h3>
      <ul>
          <li>Battery Type: Lithium-ion</li>
          <li>Cell Voltage: 3.7V</li>
          <li>Rechargeable: Yes </li>
          <li>Capacity: 1200 mAh</li>
      </ul>
    </td>
  </tr>
</table>