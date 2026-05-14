# B-Float-16
This project implements addition and subtraction of bfloat-16 floating-point numbers in Verilog and is designed for implementation on the FPGA Basys3 board.

Modules Included
MAIN Module

The main module controls the overall operation of the design.
It changes the sign bit of the second operand during subtraction, separates the operands into exponent and mantissa fields, detects special cases such as zero and exceptions, and coordinates the execution of all other modules.

COMPARE AND SHIFT Module

This module aligns the mantissas before arithmetic operations.
It compares the exponents of both operands and shifts the mantissa of the number with the smaller exponent so that proper floating-point addition or subtraction can be performed.

ADDITION Module

The addition module performs arithmetic operations based on the operand signs.
For negative numbers, 2’s complement representation is used, allowing both addition and subtraction to be executed using the same addition hardware. The output is produced in 2’s complement form when required.

NORMALISATION Module

This module converts the arithmetic result back into normalized floating-point format.
It adjusts the exponent and shifts the mantissa appropriately to maintain the standard floating-point representation with a leading 1.

Features and Enhancements
Supports special-case handling such as zero detection.
Uses edge-detection on push buttons for controlled input-triggered computation.
Allows flexible user inputs through switches, with values stored in registers for processing.
Uses 2’s complement arithmetic so that both addition and subtraction can be implemented using the same hardware modules by simply modifying the sign bit.
FPGA Implementation

To implement this design on the Basys3 FPGA board, include the top module and the appropriate constraint (.xdc) file in Vivado.
