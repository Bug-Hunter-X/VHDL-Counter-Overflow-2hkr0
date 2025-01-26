# VHDL Counter Overflow Bug

This repository demonstrates a common error in VHDL code: an integer counter that does not handle overflow conditions. The `counter.vhdl` file contains the buggy code, which increments a counter without checking if it has reached its maximum value.  The `counter_fixed.vhdl` file provides a corrected version.

## Bug Description
The original code lacks a mechanism to prevent the counter from exceeding its defined range (0 to 15). Once the counter reaches 15, the next increment will cause an overflow, leading to unpredictable results. This is a subtle bug that might only manifest under specific conditions.

## Solution
The solution involves explicitly checking for the maximum value before incrementing.  If the counter reaches 15, it is reset to 0 to avoid overflow.

## How to Reproduce
1.  Compile and simulate `counter.vhdl`. Observe the counter behavior when it reaches 15. 
2. Compile and simulate `counter_fixed.vhdl`. The counter will now correctly wrap around from 15 to 0.

This example highlights the importance of careful error handling and boundary condition checking in VHDL and other hardware description languages.