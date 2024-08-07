### UART Protocol
UART (Universal Asynchronous Receiver/Transmitter) is an asynchronous communication protocol, meaning it does not use a shared clock signal between the sender and receiver. Instead, both devices must agree on a common baud rate (bits per second) to correctly interpret the data.

### Working
- The transmitting UART receives data from a data bus.
- The data bus is used to send data to the UART from another device like a CPU, memory, or microcontroller.
- Data is transferred from the data bus to the transmitting UART in parallel form.
- After receiving the parallel data, the transmitting UART adds a start bit, a parity bit, and a stop bit, creating the data packet.
- The data packet is then output serially, bit by bit, at the Tx pin.
- The receiving UART reads the data packet bit by bit at its Rx pin.
- The receiving UART converts the data back into parallel form.
- The receiving UART removes the start bit, parity bit, and stop bits.
- The receiving UART transfers the data packet in parallel to the data bus on the receiving end.

<img src="Introduction-to-UART-Data-Transmission-Diagram.png" alt="Logo2" width="500">

### Key Feature
1. Asynchronous Communication:
   * No clock signal is shared between the devices.
   * Communication is based on agreed baud rates.
2. Full-Duplex:
   * Data can be transmitted and received simultaneously.
3. Start and Stop Bits:
   * Each data packet is framed with a start bit and one or more stop bits to signal the beginning and end of the transmission.
4. Parity Bit (Optional):
   * An optional bit used for simple error checking (even or odd parity).
5. Baud Rate:
   * Common baud rates include 9600, 14400, 19200, 38400, 57600, 115200 bps, etc.
6. UART uses only two wires to transmit data between devices.

### Data Frame Structure
A typical UART data frame consists of the following components:
1. Start Bit: Indicates the beginning of a data packet.
2. Data Bits: The actual data, usually 5 to 9 bits (commonly 8 bits).
3. Parity Bit (optional): Used for error checking.
4. Stop Bit(s): Indicates the end of a data packet, usually 1 or 2 bits.

