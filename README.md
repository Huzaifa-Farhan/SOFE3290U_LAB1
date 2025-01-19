# SOFE3290U_LAB1
Lab 1: Software Project Management and Comprehension Tool (Apache Maven)

# Binary Class Implementation

The `Binary` class is designed to represent binary numbers as strings and perform various binary operations like addition, bitwise OR, bitwise AND, and multiplication. These operations manipulate the binary digits as strings, ensuring accuracy and efficiency, even for large numbers.

## Features

- **Binary Representation**: Binary numbers are stored as strings to handle large numbers efficiently.
- **Validation**: Only '0' and '1' are accepted as valid characters. The constructor also handles empty strings and leading zeros, defaulting to "0" when needed.
- **Operations**: Supports addition, OR, AND, and multiplication, all using string manipulations and iterative procedures.
- **Efficiency**: While the operations are efficient, the frequent string concatenation in the `add` and `multiply` methods may cause performance issues for very large binary numbers.

## Operations

### 1. **Bitwise OR**

The `or` method performs a **bitwise logical OR operation** between two binary numbers. This operation compares the corresponding bits of two binary numbers, returning `1` if at least one of the bits is `1`, and `0` if both bits are `0`.

#### Steps for OR Method:
1. **Calculate Maximum Length**: Measure the lengths of both binary numbers (`num1` and `num2`) and find the maximum length.
2. **Pad Shorter String**: If one binary string is shorter, it is padded with leading zeros to match the length of the longer binary string.
3. **Bitwise OR Logic**: Use a `StringBuilder` to iterate over both binary strings and compare each corresponding pair of bits. The result is set to `1` if either bit is `1`, otherwise `0`.
4. **Return Result**: A new `Binary` object is created and returned using the final result string.

### 2. **Bitwise AND**

The `and` method performs a **bitwise logical AND operation** between two binary numbers. This operation compares the corresponding bits of two binary numbers, returning `1` if both bits are `1`, and `0` if at least one bit is `0`.

#### Steps for AND Method:
1. **Pad Shorter String**: The shorter binary number is padded with leading zeros to match the length of the longer binary number.
2. **Bitwise AND Logic**: Use a `StringBuilder` to iterate over both binary strings and compare each corresponding pair of bits. The result is set to `1` if both bits are `1`, otherwise `0`.
3. **Return Result**: A new `Binary` object is created and returned using the final result string.

### 3. **Multiplication**

The `multiply` method performs **binary multiplication**. It is similar to traditional long multiplication in decimal. The first binary number is multiplied by each bit of the second binary number, and the results are added together.

#### Steps for Multiply Method:
1. **Initialize Product**: Start with a product of "0".
2. **Iterate Over Each Bit of the Second Number**: For each bit in the second binary number (`num2`), if the bit is `1`, the first binary number (`num1`) is shifted and added to the product.
3. **Shift the First Number**: If the bit is `1`, shift the first binary number to the left by a certain number of positions and add the result to the product.
4. **Return Result**: After processing all bits of `num2`, the final product is returned.

## Testing

The provided test cases ensure that the methods in the `Binary` class work as expected. Below are the additional tests and what they verify:

### Bitwise OR Tests:
- **orSameLength**: Tests the OR operation with two binary numbers of the same length.
- **orDifferentLength**: Tests the OR operation with binary numbers of different lengths.
- **orWithZero**: Tests the OR operation with "0" as one of the binary numbers.

### Bitwise AND Tests:
- **andSameLength**: Tests the AND operation with two binary numbers of the same length.
- **andDifferentLength**: Tests the AND operation with binary numbers of different lengths.
- **andWithZero**: Tests the AND operation with "0" as one of the binary numbers.

### Multiplication Tests:
- **multiplyTwoBinaries**: Verifies that two binary numbers can be multiplied correctly.
- **multiplyWithZero**: Verifies multiplication when "0" is involved.
- **multiplyWithOne**: Verifies multiplication when "1" is involved.
