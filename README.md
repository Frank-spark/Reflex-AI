

---

# AI-Driven Modular Automation System

This repository contains the codebase for a modular, AI-driven automation system designed to operate as a flexible and adaptive solution for diverse automation tasks. The system combines edge-based AI with real-time data monitoring, dynamic UI generation, and interactive voice control, enabling non-technical users to configure and control complex automation workflows with ease.

## **Project Overview**

The AI-Driven Modular Automation System is built on four key pillars:
1. **Self-Hosted AI**: A lightweight language model interprets tasks and manages automation logic, eliminating the need for traditional programming.
2. **Modular Nodes**: Connect a variety of sensory and operational nodes (e.g., temperature, vibration, vision) to expand the AI’s monitoring and control capabilities.
3. **Dynamic UI Generation**: An image generation model creates custom user interfaces based on current tasks, enabling real-time interaction and visualization.
4. **Voice Interaction**: Speech-to-text and text-to-speech enable voice-activated control and feedback, allowing users to speak directly to the AI for setup and adjustments.

This project supports initial testing and development using **GPIO pins on the Raspberry Pi** or an **ESP32** as the control hardware.

## **Project Components**

- **Language Model (DistilBERT or GPT-Neo)**: Processes user commands and controls automation logic based on real-time node data.
- **Vosk**: An offline-capable speech-to-text model for converting voice commands to text.
- **Pyttsx3**: A text-to-speech model to provide real-time verbal feedback.
- **Image Generation Model (Stable Diffusion or Deep Daze)**: Dynamically generates custom UI components for task-specific monitoring and control.
- **Modular Nodes**: A network of sensors and output controllers for task customization, including options like temperature, vibration, and vision sensors.

## **Getting Started**

### **Prerequisites**

- **Hardware**: 
  - Raspberry Pi with GPIO setup or an ESP32 for proof of concept.
  - Compatible sensors (e.g., temperature, vibration) for initial testing.

- **Software**:
  - Python 3.7 or higher.
  - Required Python packages (detailed in `requirements.txt`):
    - `torch`, `transformers`, `vosk`, `pyttsx3`, `opencv-python`, etc.

- **Optional Hardware**:
  - Microphone for voice input.
  - Display screen for UI feedback.
  - Connected sensors and output controllers to test modular node functions.

### **Installation**

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/username/ai-driven-automation-system.git
   cd ai-driven-automation-system
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Setup Language and Voice Models**:
   - Download and configure the **DistilBERT** or **GPT-Neo** model for natural language processing.
   - Download and install the **Vosk** speech-to-text model for your language, and configure **Pyttsx3** for text-to-speech functionality.

4. **Set Up Sensors and Nodes**:
   - Connect the Raspberry Pi GPIO or ESP32 to the sensors and nodes you will use for initial testing (e.g., temperature and vibration sensors).
   - Configure pin mappings in `config.json` or directly in the code.

### **Usage**

1. **Run the Main Application**:
   ```bash
   python main.py
   ```

2. **Voice Interaction**:
   - Speak commands to the system using a microphone. The AI will interpret these commands and ask follow-up questions as needed.
   - Example commands:
     - “Monitor the motor temperature and alert me if it exceeds 85 degrees.”
     - “Adjust the vibration threshold to a lower sensitivity.”

3. **Dynamic UI Generation**:
   - Once a task is configured, the system generates a custom UI on the connected display. This UI will show relevant sensor data and allow real-time interaction with automation settings.

4. **Testing Modular Nodes**:
   - Use connected sensors to verify node integration, ensuring data is displayed in the generated UI.
   - Trigger alerts by simulating sensor threshold breaches to test predictive maintenance notifications.

### **Project Structure**

```
ai-driven-automation-system/
│
├── main.py                 # Main entry point for running the automation system
├── config.json             # Configuration file for sensor pin mappings and settings
├── requirements.txt        # Required Python packages
│
├── models/                 # Pretrained language, image generation, and voice models
│   ├── language/           # DistilBERT or GPT-Neo model files
│   ├── speech/             # Vosk model for speech-to-text
│   ├── tts/                # Pyttsx3 configuration for text-to-speech
│
├── modules/                # Modular node integration for sensors and actuators
│   ├── temperature_node.py # Temperature sensor node
│   ├── vibration_node.py   # Vibration sensor node
│   ├── vision_node.py      # Camera vision node (optional)
│
├── ui/                     # UI generation scripts and templates
│   ├── ui_generator.py     # Script to create dynamic UIs based on tasks
│   ├── templates/          # UI element templates
│
└── README.md               # Project documentation
```

### **Proof of Concept (Using GPIO or ESP32)**

1. **Raspberry Pi GPIO Setup**:
   - Connect a basic temperature sensor to GPIO pins and configure the pin mapping in `config.json`.
   - Run the application to monitor temperature data, displaying alerts when specified thresholds are exceeded.

2. **ESP32 Integration**:
   - Flash the ESP32 with firmware to communicate with the Raspberry Pi over WebSocket or MQTT.
   - Set up basic input (temperature) and output (relay) controls for testing automated alerts and responses.

### **Development Roadmap**

- **Phase 1**: Complete proof of concept with temperature and vibration monitoring using GPIO/ESP32.
- **Phase 2**: Integrate additional modular nodes and enable full voice interaction.
- **Phase 3**: Optimize UI generation and add support for camera-based vision nodes.

### **Contributing**

Contributions to improve and extend this system are welcome. Please fork the repository and create pull requests with detailed descriptions of changes.

### **License**

This project is open-source and licensed under the MIT License. Please review `LICENSE.md` for details on usage and contributions.

---
