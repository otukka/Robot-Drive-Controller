# Hardware

## Robot chassis

[Hiwonder Ackermann Steering Chassis](https://www.hiwonder.com/products/ackermann-steering-chassis?variant=40410112000087)
([wiki](https://wiki.hiwonder.com/projects/Ackermann-Chassis/en/latest/docs/1_Introduction_Installation_checked.html))

A two-layer chassis with Ackermann (car-like) steering. A servo steers
the front wheels through a linkage, and two independently driven rear wheels
give an electronic differential.

| Item            | Value |
|-----------------|-------|
| Drive motors    | 2 × 520 DC gear motor with Hall encoder, 12 V, 1:30 reduction, 6-pin cable |
| Encoder PPR     | _TODO_ |
| Steering servo  | 15 kg·cm digital PWM servo. _TODO: PWM range, steering angle limits_ |
| Motor driver    | Hiwonder motor driver board (I²C), used in the vendor's Raspberry Pi setup. _TODO: confirm what is used here_ |
| Mounting        | M3 and M4 holes |
| Wheelbase       | _TODO_ mm |
| Track width     | _TODO_ mm |
| Wheel diameter  | _TODO_ mm |

Hiwonder's own tutorials use an Arduino Uno, an STM32 controller or a
Raspberry Pi 4B. This project replaces those with the Omega2S.

## Controller board

[Onion Omega2S Eval Board](https://onion.io/store/omega2s-eval-board/)

| Item       | Value |
|------------|-------|
| Module     | Omega2S+ (MediaTek MT7688, 580 MHz MIPS) |
| Memory     | 128 MB RAM, 32 MB flash |
| OS         | OpenWrt-based Onion OS (OpenWrt 23.05) |
| Wireless   | 2.4 GHz Wi-Fi b/g/n (AP and client modes) |
| I/O        | GPIO, PWM, I²C, UART on the expansion headers; USB 2.0 host, microSD, Ethernet |
| Power/console | USB-C (power and serial console) |
| Logic level | 3.3 V. The GPIOs are not 5 V tolerant. |

See the [Omega2S Eval Board pinout](https://onion.io/wp-content/uploads/2025/01/omega2s-eval-board-pinout.svg).

For how the two are connected, see [wiring.md](wiring.md).
