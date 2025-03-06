# TecDev-Ohmmeter
Automatic Ohmmeter - A New Approach

![TecDev-Ohmmeter](https://github.com/Tecfield-SIA/TecDev-Ohmmeter/blob/main/Images/1.jpg)

________________________________________

## Introduction

This project introduces an innovative automatic ohmmeter that eliminates the need for high-side switching and diodes, providing a more accurate and efficient resistance measurement. Unlike traditional voltage divider-based ohmmeters that suffer from voltage drops due to series diodes, this design employs low-side switching using logic-gate MOSFETs, resulting in minimal voltage loss and improved precision.

________________________________________

## How It Works

Traditional ohmmeters use a high-side switch controlled by a microcontroller, where the reference resistors are connected in series with an unknown resistor. However, to prevent backflow of current into the microcontroller, diodes are placed in series, causing a significant voltage drop, especially in low-voltage systems. My approach replaces this with:

- A constant and stable 3.3V current source to power the unknown resistor.
- Reference resistors placed after the unknown resistor, switching to ground through logic-gate MOSFETs controlled by the microcontroller.
- Automatic resistance detection, as the system continuously reads the analog pin. Once a resistor is placed in the circuit, the microcontroller immediately detects and starts the measurement cycle.

________________________________________

## Key Advantages

- No diode voltage drop, leading to significantly improved accuracy.
- Automatic detection of the unknown resistor, eliminating the need for manual triggering.
- High-speed operation due to MOSFET switching.
- Protects the microcontroller, as current never flows directly into it.
- Scalable accuracy, by increasing the number of reference resistors.
- Can be used as a noise detector, as environmental noise may trigger readings when no resistor is present.
- Can measure skin resistance by simply touching the test pads.

________________________________________

## Technical Specifications

- Resistance range: 0Ω to 20MΩ (scalable with more reference resistors).
- Accuracy: ~98%, expandable to 99%+ with additional reference resistors.
- Microcontroller: STM32F030K6T6.
- Firmware: Developed in C++ using Arduino IDE.
- Display: 0.96” OLED screen.
- Power: USB-C input, regulated by MIC5219 to 3.3V.
- Physical dimensions: 7cm × 3cm.
- Safety features: Zener diode for overvoltage protection, resettable fuse for overcurrent protection, ferrite beads for EMI reduction.

________________________________________

## Design & Development Challenges

- Limited Flash Memory: The STM32F030K6T6 has a small program memory, requiring optimized code. A lightweight SSD1306 library was developed to fit within the constraints.
  - [lightweight SSD1306 library](https://github.com/Tecfield-SIA/Lightweight_SSD1306)
- Precision Calibration: The reference resistors are software-configurable, allowing for fine-tuned calibration using predefined values and a user-adjustable correction factor.
- Aesthetic Enhancements: Power indicator LEDs provide a smooth lighting effect upon power-on.

________________________________________

## Future Improvements

- Higher accuracy: Increasing the number of reference resistors to achieve 99.9% accuracy.
- Optimized measurement algorithm: Enhancing the selection of the best reference resistor for more precise readings.

________________________________________

## Note

The firmware will be released soon after minor refinements. Stay tuned!

________________________________________

## License

This project is released under Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0). Feel free to use and modify it for personal or educational purposes, but commercial use requires my permission.

📌 Original Concept & Development: Siavash Alizadeh

📌 GitHub Repository: https://github.com/Tecfield-SIA/TecDev-Ohmmeter/tree/main

________________________________________

## Conclusion

- This project demonstrates an innovative method for designing an automatic ohmmeter with improved accuracy and usability. The design is minimalistic yet highly effective, making it a great addition to any electronics toolkit. Future iterations will refine and expand upon this concept for even greater precision and functionality.

Feel free to explore, contribute, and share your feedback!

__Contact__

For questions or discussions, feel free to open an issue or reach out via LinkedIn or email me at Tecfield@live.com.
www.linkedin.com/in/siavash-alizadeh-tecfield
