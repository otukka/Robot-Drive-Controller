# Robot-Drive-Controller

Drive controller for a Hiwonder Ackermann steering robot chassis, running on an
Onion Omega2S embedded Linux board.

The controller receives speed and steering commands from a ROS 2 PC over Wi-Fi
or Ethernet. It turns them into signals for the chassis' drive motor driver and
steering servo, and sends wheel encoder feedback and status back to the PC.

## Documentation

- [Hardware](docs/hardware.md): chassis and controller board specs
- [Architecture](docs/architecture.md): system overview, PC link, failsafe
- [Wiring](docs/wiring.md): pin assignments and power
- [Getting started](docs/getting-started.md): build, deploy, run
- [Configuration](docs/configuration.md): network and vehicle parameters

## License

See [LICENSE](LICENSE).
