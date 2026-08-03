# Running LEDs

## Objectives

- Configure multiple GPIO pins as digital outputs.
- Control multiple LEDs independently.
- Store LED GPIO ports and pins in arrays.
- Use loops to reduce repeated GPIO operations.
- Create a bidirectional running-light pattern.
- Understand how software delays affect the animation speed.

## Hardware

- Board: NUCLEO-F446RE
- Multiple external LEDs
- Current-limiting resistors
- Breadboard and jumper wires

## Expected Behavior

The LEDs turn on one after another from the first LED to the last LED.

After reaching the last LED, the sequence reverses and moves back toward the first LED.

The back-and-forth running-light pattern repeats continuously.

```text
LED1 → LED2 → LED3 → LED4 → LED5 → LED4 → LED3 → LED2 → LED1 → ...
```

The LED GPIO ports and pins are stored in arrays, allowing each LED to be accessed by its array index and controlled using loops. The number of LEDs can be changed by adding or removing array elements without rewriting the control logic.
