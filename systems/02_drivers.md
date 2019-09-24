## Device Drivers
- A device driver refers to software
- A device driver is a computer program that operates or controls a particular type of device that is attached to a computer
- The role of a device driver is to work as a translator between a hardware device and any application or the operating system that uses it

## Device Controllers
- A device controller refers to physical hardware
- A device controller is a system that handles the incoming and outgoing signals of the CPU
- A device is connected to the computer via a plug and socket, and the socket is connected to a device controller
- A device controller converts a serial bit stream to a block of bytes and performs error correction as required
- All controllers are connected to the CPU via the common bus
- Examples:
	- The memory is connected to a memory controller
	- The monitor is connected to a video controller
	- The keyboard is connected to a keyboard controller
	- The disk drive is connected to a disk controller
	- The USB drive is connected to a USB controller

## Life Cycle of Device Controllers
1. A device controller receives data from a connected device
2. The device controller stores that data temporarily in a special purpose register called a local buffer inside the controller
3. Each device controller has a corresponding device driver, which then receives the interpreted signals from the its controller

## References
- https://pediaa.com/what-is-the-difference-between-device-driver-and-device-controller/
