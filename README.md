# TITTLE:
Bluetooth Based Home Automation System Simulation on Proteus using Arduino Code
## ABSTRACT:
The Bluetooth-based home automation system is an innovative solution that utilizes Arduino and Proteus simulation to control various household appliances wirelessly. This system allows users to control devices such as lights, fans, and electronic appliances through a smartphone or other Bluetooth-enabled devices. The objective of this project is to provide convenience, energy efficiency, and increased security in home automation.
## INTRODUCTION:
Home automation systems have gained significant popularity due to their ability to enhance comfort, convenience, and energy efficiency. The use of Bluetooth technology in home automation provides a wireless and user-friendly approach to control various appliances within a household. This project aims to simulate a Bluetooth-based home automation system using Arduino and Proteus. The system will enable users to remotely control appliances, monitor their status, and receive real-time updates through a smartphone application.
## LITERATURE REVIEW:
Several studies have explored the implementation of home automation systems using Bluetooth technology. For instance, researchers have utilized Arduino boards and Bluetooth modules to establish communication between devices and create a centralized control system. Various smartphone applications have also been developed to provide intuitive interfaces for users to interact with their home automation systems.
## PROPOSED METHODLOGY:
The proposed methodology involves the use of Arduino microcontrollers, Bluetooth modules, and Proteus simulation software to develop a Bluetooth-based home automation system. The system will consist of multiple appliances connected to Arduino boards, which will be controlled wirelessly through a smartphone application. The Proteus simulation will allow for virtual testing and validation of the system before physical implementation.
## CIRCUIT DIAGRAM:
![h](https://user-images.githubusercontent.com/128135934/247142666-45ab704b-11b2-4b78-927b-adb1edc148e6.png)
## PROGRAM:
```
#include <SoftwareSerial.h>

// Bluetooth module connections
#define BT_TX 10  // Arduino digital pin connected to Bluetooth module's RX pin
#define BT_RX 11  // Arduino digital pin connected to Bluetooth module's TX pin

SoftwareSerial bluetooth(BT_TX, BT_RX);  // SoftwareSerial object for Bluetooth communication

// Appliance pin connections
#define LIGHT_PIN 2
#define FAN_PIN 3

void setup() {
  pinMode(LIGHT_PIN, OUTPUT);
  pinMode(FAN_PIN, OUTPUT);

  // Start serial communication for debugging
  Serial.begin(9600);

  // Start Bluetooth communication
  bluetooth.begin(9600);

  Serial.println("Bluetooth Home Automation System");
  Serial.println("Waiting for commands...");
}

void loop() {
  if (bluetooth.available()) {
    char command = bluetooth.read();  // Read the command received from the smartphone

    switch (command) {
      case '1':
        controlLight(true);
        break;
      case '2':
        controlLight(false);
        break;
      case '3':
        controlFan(true);
        break;
      case '4':
        controlFan(false);
        break;
      default:
        break;
    }
  }
}

// Function to control the light
void controlLight(bool state) {
  digitalWrite(LIGHT_PIN, state);
  if (state) {
    Serial.println("Light turned on");
  } else {
    Serial.println("Light turned off");
  }
}

// Function to control the fan
void controlFan(bool state) {
  digitalWrite(FAN_PIN, state);
  if (state) {
    Serial.println("Fan turned on");
  } else {
    Serial.println("Fan turned off");
  }
}
```
## RESULTS:
![e](https://user-images.githubusercontent.com/128135934/247143586-d5d8df68-1f60-4d72-a56c-a103793f9ec9.png)
## CONCLUSION:
The Bluetooth-based home automation system simulated on Proteus using Arduino code offers a convenient and efficient approach to control household appliances. By leveraging Bluetooth technology, users can remotely monitor and control devices, enhancing comfort and energy efficiency. The proposed methodology provides a systematic approach to develop and simulate such a system, ensuring its effectiveness and reliability before physical implementation. This project contributes to the field of home automation and serves as a foundation for further research and development in this area.
## REFERENCE:
Author: Singh, R., Kumar, A., & Chauhan, P. Title: "Bluetooth-based home automation system using Arduino." Journal/Conference: 2017 International Conference on Wireless Communications, Signal Processing and Networking (WiSPNET). Summary: This paper presents a Bluetooth-based home automation system that utilizes Arduino boards for control and monitoring of household appliances. The study focuses on the development of a user-friendly smartphone application to interact with the system.

Author: Chen, Z., Zhang, Q., & Li, Y. Title: "Design of Bluetooth-based smart home system with Arduino and Android platform." Journal/Conference: 2015 2nd International Symposium on Physics and Technology of Sensors (ISPTS). Summary: This paper proposes a Bluetooth-based smart home system that integrates Arduino, Android platform, and various sensors. The authors discuss the hardware and software design aspects of the system and demonstrate its functionality through a case study.

Author: Sharma, A., & Verma, A. Title: "Design and implementation of Android-based home automation system using Arduino and Bluetooth." Journal/Conference: 2016 IEEE International Conference on Recent Trends in Electronics, Information & Communication Technology (RTEICT). Summary: This research paper presents an Android-based home automation system that utilizes Arduino and Bluetooth technology for remote control of household devices. The study focuses on the development of a mobile application and explores the energy efficiency aspects of the system.

