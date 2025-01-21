# 4-BIT SEQUENTIAL MULTIPLIER
=

A **4-bit sequential multiplier** is a digital circuit designed to perform multiplication of two 4-bit binary numbers. Instead of using combinational logic to perform the multiplication all at once, it processes the multiplication sequentially, one bit at a time, using shift-and-add techniques.

#### Key Components:
1. **Registers**: 
   - To hold the multiplier (`B`), multiplicand (`A`), and the partial product.
   - A shift register for the multiplier is often used.

2. **Accumulator**: 
   - To store the intermediate and final result (partial products).

3. **Control Logic**: 
   - Manages the sequencing of operations and ensures proper timing.

4. **Adder**: 
   - Performs addition of the shifted multiplicand and the partial product.

5. **Clock Signal**: 
   - Drives the sequential operations.

#### Working Principle:
1. **Initialization**:
   - Load the multiplicand (`A`) and multiplier (`B`) into their respective registers.
   - Set the accumulator to zero.

2. **Sequential Multiplication**:
   - For each bit of the multiplier:
     - Check the least significant bit (LSB) of the multiplier.
     - If the LSB is `1`, add the multiplicand to the partial product (stored in the accumulator).
     - Shift the multiplier to the right by one bit.
     - Shift the multiplicand to the left by one bit (optional, depending on implementation).

3. **Completion**:
   - After processing all bits of the multiplier, the accumulator holds the final product.

#### Example Operation:
For `A = 1101` (13 in decimal) and `B = 1011` (11 in decimal):
- Initialize:
  - Multiplier `B = 1011`
  - Multiplicand `A = 1101`
  - Accumulator = `0000`

- Sequential steps:
  1. Add `A` to accumulator (if LSB of `B` is 1), then shift.
  2. Repeat for each subsequent bit of `B`.

- Final product in the accumulator: `10001111` (143 in decimal).

#### Advantages:
- **Reduced Hardware**: Uses fewer gates compared to a combinational multiplier.
- **Scalability**: Can be extended to multiply larger numbers by adjusting registers and control logic.

#### Disadvantages:
- **Speed**: Slower than a combinational multiplier due to sequential processing.
- **Complex Control Logic**: Requires additional logic for sequencing.

#### Applications:
- Used in embedded systems where hardware resources are limited.
- Useful in low-power and cost-sensitive applications, such as microcontrollers or digital signal processing.
