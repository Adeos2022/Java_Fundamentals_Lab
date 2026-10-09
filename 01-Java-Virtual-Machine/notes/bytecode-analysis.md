# JVM Bytecode Analysis: Addition vs Subtraction

## Objective

Observe how Java arithmetic operators are represented in JVM bytecode.

## Addition

Source expression:

    int result = a + b;

Observed arithmetic instruction:

    iadd

## Subtraction

Source expression:

    int result = a - b;

Observed arithmetic instruction:

    isub

## Operand Stack

The JVM loads the two integer operands onto the operand stack.
The arithmetic instruction consumes both operands and pushes the result.

For subtraction, the top stack value is subtracted from the value beneath it.

## Results

With a = 10 and b = 20:

- Addition: 10 + 20 = 30
- Subtraction: 10 - 20 = -10

## Conclusion

The Java compiler translates arithmetic expressions into JVM bytecode.
The `iadd` instruction performs integer addition, while `isub` performs
integer subtraction.

## Tools

- javac: compiles Java source code
- java: launches the program
- javap -c: disassembles bytecode
