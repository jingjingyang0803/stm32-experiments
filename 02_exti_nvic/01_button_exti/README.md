# 01_button_exti

This experiment uses the onboard USER button of the NUCLEO-F446RE to toggle the onboard green LED through an external interrupt.

The USER button is connected to `PC13`, and the green LED is connected to `PA5`.

## Hardware

- NUCLEO-F446RE
- USB cable

No external components are required.

## GPIO configuration

### USER_BUTTON

- Pin: `PC13`
- Mode: `GPIO_EXTI13`
- Trigger: Rising edge
- Pull-up/Pull-down: `No pull`
- User Label: `USER_BUTTON`

On the NUCLEO-F446RE, the USER button input is low while the button is pressed and returns high when the button is released. Therefore, the interrupt is configured for a rising edge so that the LED state changes when the button is released.

```text
Button pressed:  LOW
Button released: LOW -> HIGH
```

### LED_GREEN

- Pin: `PA5`
- Mode: `GPIO_Output`
- Output type: `Push-Pull`
- Pull-up/Pull-down: `No pull`
- Speed: `Low`
- Initial output level: `Low`
- User Label: `LED_GREEN`

## NVIC configuration

Enable:

```
EXTI line[15:10] interrupts
```

`PC13` uses EXTI line 13. EXTI lines 10 through 15 share the same NVIC interrupt handler:

```
EXTI15_10_IRQn
```

## Interrupt flow

```
PC13 rising edge on button release
-> EXTI13 interrupt request
-> NVIC handles EXTI15_10_IRQn
-> EXTI15_10_IRQHandler()
-> HAL_GPIO_EXTI_IRQHandler()
-> HAL_GPIO_EXTI_Callback()
```

## Software debounce

Mechanical buttons may generate several rapid signal transitions when they are pressed or released. This is called contact bounce.

The interrupt callback uses `HAL_GetTick()` to ignore events that occur within 50 milliseconds of the previous accepted release.

The debounce implementation is located in `main.c`.

Do not use `HAL_Delay()` inside the interrupt callback because it blocks interrupt processing and depends on the system tick.

## Behavior

Each valid button release toggles the onboard green LED:

```
First release  -> LED on
Second release -> LED off
Third release  -> LED on
```

The button is handled through an external interrupt rather than continuous polling.
