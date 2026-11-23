# Wiring

| Omega2S pin | Signal            | Chassis connection |
|-------------|-------------------|--------------------|
| _TODO_      | Steering PWM      | Servo signal       |
| _TODO_      | I²C SDA / SCL (if the I²C driver board is used) | Motor driver |
| _TODO_      | Motor PWM / DIR (if a PWM driver is used)       | Motor driver |
| _TODO_      | Encoder A/B (if not read by the driver board)   | Motor encoder |
| GND         | Ground            | Common ground with the chassis |

## Power

- Power the servo and motors through the driver board, not from the Omega2S.
- Give the Omega2S its own supply, as Hiwonder recommends for the Raspberry Pi.
- Connect all grounds together.
- Use level shifting for any 5 V signal that goes into the Omega2S.
