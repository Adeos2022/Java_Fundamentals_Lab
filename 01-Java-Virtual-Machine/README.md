# Lab 01: The Java Virtual Machine

## Objective

Understand how Java source code is compiled into bytecode and
executed by the Java Virtual Machine.

## Environment

- OpenJDK 21
- Termux on Android
- Java compiler: javac
- Bytecode inspection tool: javap

## Source Code

See [Addition.java](Addition.java).

The program declares two integer variables, adds them, and prints
the result.

## Procedure

Compile the source code:

    javac Addition.java

Run the compiled program:

    java Addition

Inspect the bytecode:

    javap -c Addition

## Expected Output

    Answer: 30

## Observations

1. `Addition.java` contains human-readable Java source code.
2. `javac` compiles the source into `Addition.class`.
3. The class file contains Java bytecode.
4. The `java` launcher starts the JVM to execute the program.
5. `javap -c` displays bytecode instructions for inspection.

## Bytecode Findings

| Instruction | Purpose |
|---|---|
| `bipush` | Pushes a small integer onto the operand stack |
| `istore` | Stores an integer in a local variable slot |
| `iload` | Loads an integer from a local variable slot |
| `iadd` | Adds two integers |
| `getstatic` | Retrieves a static field, such as `System.out` |
| `invokevirtual` | Invokes an instance method, such as `println` |
| `return` | Returns from the current method |

The compiler may use additional instructions, including
`invokedynamic`, for string concatenation.

## Key Lesson

Java source code is compiled into platform-independent bytecode.
A compatible JVM executes that bytecode on the target platform.

## Further Experiments

- Change addition to subtraction and inspect the bytecode.
- Change the integer values and observe the output.
- Compare bytecode before and after modifying the program.

## Status

Initial compilation, execution, and bytecode inspection completed.
