# PWM_CYCLONE_IV_FPGA
# PWM Generator with Adjustable Duty Cycle

## Overview
This project implements a high-frequency PWM (Pulse Width Modulation) signal generator with an adjustable duty cycle using VHDL. The system is designed for FPGA implementation and features real-time duty cycle control via push buttons with integrated debouncing.

## Features
- High-frequency PWM output (10 MHz)
- Adjustable duty cycle (10% step increments/decrements)
- Debounce mechanism for stable user input
- Optimized for FPGA clock input (100 MHz)

## System Architecture
The design is structured into modular components:
1. Clock Divider – Generates a slow clock signal for button debouncing.
2. Debounce Circuit – Ensures reliable button press detection using D Flip-Flops.
3. Duty Cycle Controller – Adjusts the PWM duty cycle based on user input.
4. PWM Generator – Produces the final modulated output signal.

### Block Diagram
```
+----------------+       +--------------------+       +-----------------+
| Clock Divider  | --->  |  Debounce Circuit  | --->  | Duty Cycle Ctrl |
+----------------+       +--------------------+       +-----------------+
                                                  |
                                                  v
                                          +-----------------+
                                          |  PWM Generator  |
                                          +-----------------+
                                                  |
                                                  v
                                          +-----------------+
                                          |    PWM_OUT      |
                                          +-----------------+
```

## Implementation
### Hardware Requirements
- FPGA development board (100 MHz clock input)
- Two push buttons for duty cycle control
- External display or oscilloscope to observe PWM output

### Software & Tools
- VHDL Compiler & Simulator (ModelSim, Quartus, Vivado, etc.)
- FPGA Programming Environment

## Usage
1. Load the `PWM_Controller.vhd` and `DFF_Debounce.vhd` files into your FPGA project.
2. Compile and synthesize the design.
3. Upload the bitstream to your FPGA board.
4. Use the dedicated buttons to increase or decrease the duty cycle.
5. Observe the PWM waveform on an oscilloscope or logic analyzer.

## Testing & Validation
- Functional simulation using testbenches.
- Hardware validation using FPGA implementation.
- Real-time duty cycle adjustments verified via oscilloscope.

## Author
- Mohamed El Jazouly 
  Embedded Systems Engineer  
  ENSAM Rabat  
  Email: mohamed.eljazouly@usmba.ac.ma  

## License
This project is open-source and free to use for educational and research purposes.

