# Smart Water Dispensing Assistant

## Latest Project Idea

A voice-controlled automatic water dispenser designed to help a patient request and receive a measured glass of water.

### Core flow

1. Patient asks the voice assistant for water.
2. Assistant asks the patient to place the glass correctly.
3. A 10 kg load cell connected to an HX711 detects the glass and waits for a stable reading.
4. The current glass weight is used as the tare/baseline.
5. The motor or pump starts dispensing water.
6. The load cell continuously measures the increase in weight.
7. Water amount is calculated from the increase in weight:
   - approximately 1 g water ≈ 1 mL water
   - example: 250 g increase ≈ 250 mL
8. The pump stops when the requested amount is reached.

### Safety conditions

- Glass removed → pump OFF
- Sudden weight drop → pump OFF
- Target water weight reached → pump OFF
- Pump running but weight not increasing → pump OFF
- Maximum dispensing time exceeded → pump OFF

### Hardware

- ESP32
- HX711 load-cell amplifier module
- 10 kg load cell
- Water pump/motor
- Motor driver or suitable pump controller
- Glass/platform mounted on the load cell

### Design note

The system should measure the **increase in weight after taring the empty glass**, rather than relying on a fixed total weight. This allows different glass weights to be handled.

Status: Idea saved for development.
