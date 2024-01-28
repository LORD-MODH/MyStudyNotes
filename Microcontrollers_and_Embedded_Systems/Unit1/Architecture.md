# 8051 Microcontroller Architecture

## ALU (Arithmetic Logic Unit)
- **Bit Size**: 8-bit unit.
- **Functions**:
  - **Arithmetic Operations**: Addition, subtraction, multiplication, division, increment, and decrement.
  - **Logical Operations**: AND, OR, EX-OR.
  - **Data Manipulation**: Handles both 8-bit and 16-bit data.

## Accumulator
- **Bit Size**: 8-bit register.
- **Address**: E0H, bit and byte accessible.
- **Function**: Stores the result of arithmetic and logic operations performed by the ALU.

## B-register
- **Usage**: Stores one operand for multiply and divide instructions.
- **Type**: Special 8-bit maths register.
- **Accessibility**: Bit and byte accessible.
- **Function**: Used in conjunction with the A register as input operand for the ALU. Also serves as a general-purpose register for storing 8-bit data.

## PSW (Program Status Word)
- **Bit Size**: 8-bit register.
- **Address**: D0H, bit and byte accessible.
- **Components**:
  - **Carry Flag (CY)**: Set on carry or borrow during addition/subtraction.
  - **Auxiliary Carry Flag (AC)**: Set on carry/borrow from lower to higher 4 bits during addition/subtraction.
  - **F0**: User-defined general-purpose flag bit.
  - **Overflow Flag (OV)**: Set if signed arithmetic operation results exceed 7 bits.
  - **Parity Flag (P)**: Set for even parity (even number of ones); resets for odd parity.
  - **RS1 and RS0**: Register Bank Selection flags.

## Program Counter (PC)
- **Bit Size**: 2-byte address.
- **Function**: Indicates the memory address of the next instruction to execute. Initializes at 0000 H and increments after each instruction execution.

## Data Pointer Register (DTPR)
- **Bit Size**: 16-bit register.
- **Components**:
  - **DPH (Data Pointer Higher Order)**
  - **DPL (Data Pointer Lower Order)**
- **Function**: Holds the address of external/internal RAM for data storage.

## Stack Pointer (SP)
- **Bit Size**: 8-bit register, byte addressable.
- **Function**: Manages data placement on the stack. Increments by 1 during a push instruction, decrements by 1 during a pop instruction.

## Ports (P0, P1, P2, P3)
- **Type**: Input/output ports (Port0, Port1, Port2, Port3).
- **Function**: Each bit of these Special Function Registers (SFR) corresponds to a pin on the microcontroller. Writing 1 or 0 to a bit sets the corresponding I/O pin to high or low level, respectively.

## Serial Data Buffer
- **Type**: Consists of two independent registers.
  - **Transmit Buffer**: Parallel in, serial out register.
  - **Receive Buffer**: Serial in, parallel out register.
- **Function**: Loading a byte to the transmit buffer initiates serial transmission. Reading from SBUF reads received serial data.
- **Identification**: Known as SBUF.

## Timer Registers
- **Description**: Two 16-bit registers accessible as lower and upper bytes.
- **Components**:
  - **TL0**: Lower byte of timer register 0.
  - **TH0**: Higher byte of timer register 0.
  - **TL1**: Lower byte of timer register 1.
  - **TH1**: Higher byte of timer register 1.

## Control Registers
- **Registers**: Includes IP, OE, TMOD, TCON, SCON, and PCON.
- **Function**: Contains control and status information for interrupts, timers/counters, and the serial port.

## Timing and Control Unit
- **Function**: Generates necessary timing and control signals for internal operations and external system bus control.

## Oscillator
- **Function**: Generates the basic timing clock signal for circuit operations using a crystal oscillator.

## Instruction Register
- **Function**: Decodes the opcode of an instruction and informs the timing and control unit to generate necessary execution signals.

## EPROM and Program Address Register
- **Features**: Provides on-chip EPROM and a mechanism for internal addressing.

## RAM and RAM Address Register
- **Features**: Provides internal 128 bytes of RAM and a mechanism for internal addressing.

## Power Control Register (PCON)
- **Bit Size**: 8-bit, byte addressable.
- **Components**:
  - **SMOD**: Serial baud rate modify bit.
  - **PD**: Power down mode.
  - **GF1**: General purpose user flag bit 1.
  - **IDL**: Idle mode.
  - **GF0**: General purpose user flag bit 0.
- **Modes**:
  - **Idle Mode**: Exited by hardware reset; CPU resumes from the next instruction after 'Idle' invocation.
  - **Power Down Mode**: Internal clock is stopped; exited by hardware reset; CPU resumes from the next instruction after Power Down Mode invocation.

## 8051 Clock and Instruction Cycle
- **Core**: Circuitry generates clock pulses for synchronizing internal operations.
- **Pins**: XTAL1 and XTAL2 for connecting the resonator.
- **Crystal Frequency**: Basic internal frequency, typically 11.04962 MHz; operable between 1MHz to 16MHz.


