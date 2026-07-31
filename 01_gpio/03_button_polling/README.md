# Button Polling

## Objectives

- Configure a GPIO pin as a digital input.
- Read the onboard USER button using polling.
- Toggle the onboard LED after a valid button press.
- Implement simple software debouncing.
- Prevent repeated triggering while the button remains pressed.
- Observe the valid button press count using the debugger.

## Hardware

- Board: NUCLEO-F446RE
- Button: Onboard USER button B1
- Button GPIO: PC13
- LED: Onboard user LED LD2
- LED GPIO: PA5

## Expected Behavior

Each valid button press toggles the onboard LED.

- First press: LED turns on.
- Second press: LED turns off.
- Holding the button does not repeatedly toggle the LED.
