# Special Function Registers (SFRs) of 8051 Microcontroller

## Overview
- **Location**: Mapped in the upper 128 bytes of internal data memory (80H to FFH).
- **Access**: Direct addressing only.
- **Bit Addressability**: Some SFRs are also bit addressable, allowing specific bits to be altered without changing others.
- **Address Range**: 80H to FFH.

## Key SFRs

### 1) TMOD (Timer Mode Register)
- **Type**: 8-bit register.
- **Function**: Sets various timer operation modes for both timers.
- **Structure**: Lower 4 bits for Timer 0, upper 4 bits for Timer 1.
- **Components**:
  - **Gate**: START/STOP of Timer/Counter.
  - **C/T**: Counter/Timer selection.
  - **M1 & M0**: Mode selection bits.
- **Modes**:
  - **Timer 1 / Timer 0**:
    - **0 0**: Mode 0 (13-bit timer mode).
    - **0 1**: Mode 1 (16-bit timer mode).
    - **1 0**: Mode 2 (8-bit auto reload).
    - **1 1**: Mode 3 (Split timer mode).

### 2) TCON (Timer Control Register)
- **Type**: 8-bit register.
- **Components**:
  - **Upper 4 Bits**: Store TF and TR bits for Timer 0 and Timer 1.
  - **Lower 4 Bits**: Control interrupt bits.
  - **TF1/TR1**: Timer1 overflow flag/run control bit.
  - **TF0/TR0**: Timer0 overflow flag/run control bit.
  - **IE1/IE0**: Interrupt edge flags.
  - **IT1/IT0**: Interrupt type control bits.

### 3) SBUF (Serial Buffer Register)
- **Type**: 8-bit register.
- **Function**: Separate registers for data transmission and reception.
- **Usage**: Holds data for TXD line transmission and data received by RXD pin.

### 4) SCON (Serial Control Register)
- **Type**: 8-bit register.
- **Components**:
  - **Mode Selection Bits**: SM0, SM1.
  - **Serial Port Interrupt Bits**: TI, RI.
  - **Ninth Data Bit**: TB8 (transmitted), RB8 (received).
- **Modes**:
  - **0 0**: Mode 0 (Shift Register, fosc/12).
  - **0 1**: Mode 1 (8 Bit UART, Variable).
  - **1 0**: Mode 2 (9 Bit UART, fosc/32 or fosc/64).
  - **1 1**: Mode 3 (9 Bit UART, Variable).
- **Additional Flags**:
  - **SM2**: Multiprocessor communication.
  - **REN**: Reception enable/disable.
  - **TI/RI**: Transmit/Receive Interrupt Flag.

### 5) PCON (Power Mode Control Register)
- **Type**: 8-bit register.
- **Function**: Controls power down, sleep modes, and serial data baud rate.
- **Components**:
  - **SMOD**: Serial baud rate modify bit.
  - **PD**: Power down mode.
  - **GF1/GF0**: General purpose user flag bits.
  - **IDL**: Idle Mode.
