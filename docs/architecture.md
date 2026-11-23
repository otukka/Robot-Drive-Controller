# Architecture

```
     ROS 2 PC                              Omega2S                          chassis
┌──────────────────┐   Wi-Fi /    ┌────────────────────┐
│ ROS 2 nodes      │   Ethernet   │ network interface  │
│ (nav, teleop...) │◀────────────▶│ drive controller   │── I²C or PWM ▶ motor driver ──▶ rear motors
│ bridge node      │  commands ▶  │ steering control   │── PWM ──────▶ steering servo
└──────────────────┘  ◀ feedback  │ odometry, failsafe │◀── encoders ─ rear motors
                                  └────────────────────┘
```

The Omega2S doesn't run a full ROS 2 stack. With a MIPS CPU and 128 MB of RAM it
is too small. ROS 2 runs on the PC, and the controller talks to it over the
network. Either link can be used: Wi-Fi (client or AP mode) or the eval board's
Ethernet port.

## Transport

The controller speaks a lightweight custom protocol. A bridge node on the PC
translates between that protocol and ROS 2 topics, so the controller has no ROS
dependencies. micro-ROS on the Omega2S is not an option.

_TODO: define the protocol (UDP recommended) and message format._

## Messages

**PC → controller:** velocity and steering commands (e.g. from `cmd_vel` or
`ackermann_msgs/AckermannDrive`).

**Controller → PC:** wheel encoder counts or odometry, plus status.

## Failsafe

The controller stops the motors and centres the steering when commands stop
arriving within a timeout. This also covers a dropped Wi-Fi link.
