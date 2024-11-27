
# Line-Following Robot with Raspberry Pi Pico

This repository contains the Python code for a line-following robot using the Raspberry Pi Pico. The robot uses an array of IR sensors to detect the line and adjust its motor speed and direction for following the path.

## Features

- Uses 5 IR sensors for line detection.
- Controls two DC motors using PWM for speed and direction.
- Implements logic for sharp turns, slight turns, and straight movements.

## Prerequisites

### Hardware Requirements:
1. **Raspberry Pi Pico**
2. **5 IR sensors**
3. **Motor driver module** (e.g., L298N or similar)
4. **DC motors** (2 units)
5. Power source (e.g., battery or USB power)
6. Connecting wires and chassis

### Software Requirements:
1. **MicroPython** installed on Raspberry Pi Pico.
2. **Thonny IDE** (or any compatible MicroPython IDE).

## Wiring

| Component      | Raspberry Pi Pico Pin | Description                        |
|----------------|------------------------|------------------------------------|
| IR Sensors     | GPIO Pins (0 to 4)    | Connect to pins 0, 1, 2, 3, and 4 |
| Motor A (Left) | GPIO Pins (Replace `PIN`) | Set `ain1`, `ain2`, and PWM for motor A |
| Motor B (Right)| GPIO Pins (Replace `PIN`) | Set `bin1`, `bin2`, and PWM for motor B |
| GND            | GND Pin               | Common ground for all components  |

### Pin Configuration

Replace all `PIN` placeholders in the code with actual GPIO pin numbers that you have wired.

## Setup Instructions

1. Clone the repository or download the code:
    ```bash
    git clone https://github.com/your-username/line-follower-pico.git
    cd line-follower-pico
    ```

2. Open the code in Thonny IDE.

3. Replace the `PIN` placeholders in the code with your specific pin numbers for:
   - **Motor control pins** (`ain1`, `ain2`, `bin1`, `bin2`).
   - **PWM pins** (`pwm_a`, `pwm_b`).

4. Upload the script to the Raspberry Pi Pico.

5. Power the Pico and test the robot on a line-following track.

## Usage

- Place the robot on a track with a black line on a white surface (or vice versa).
- Power up the robot.
- The robot will start following the line based on the sensor inputs.

## Code Overview

### Functions

- **`read_sensors()`**: Reads values from all IR sensors.
- **`set_motor_speed(left_speed, right_speed)`**: Sets speed and direction for the left and right motors.
- **`stop()`**: Stops both motors.
- **`forward()`**: Moves the robot forward.
- **`turn_left()` and `turn_right()`**: Handles turning movements.
- **`line_follower_logic()`**: Implements line-following logic based on sensor readings.

### Main Loop

The main loop continuously calls `line_follower_logic()` to evaluate sensor data and adjust motor speed/direction accordingly.

## Customization

- **Speed**: Adjust the `speed` variable to modify the robot's default speed.
- **Logic**: Customize `line_follower_logic()` to suit your specific track design or sensor arrangement.

## Debugging

- Use the `print()` statements in the code to debug sensor values and motor control logic.
- Ensure all connections are secure and the track contrast is sufficient for the IR sensors.

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
