# 04_buzzer_and_sensor

This experiment uses an SW-520D gravity tilt switch module to control an active buzzer.

When the internal mechanical switch closes, the module outputs a low level on `DO`. The buzzer and the module's `DO-LED` are then turned on.

## Hardware

- NUCLEO-F446RE
- SW-520D gravity tilt switch module
- Three-pin active buzzer module
- Jumper wires

## Connections

### SW-520D module

| SW-520D | NUCLEO-F446RE            |
| ------- | ------------------------ |
| VCC     | 3.3V                     |
| GND     | GND                      |
| DO      | `TILT_SENSOR` GPIO input |

### Active buzzer module

| Buzzer   | NUCLEO-F446RE        |
| -------- | -------------------- |
| VCC      | 3.3V                 |
| GND      | GND                  |
| IN / SIG | `BUZZER` GPIO output |

All modules must share a common ground.

## GPIO configuration

### TILT_SENSOR

- Mode: `GPIO_Input`
- Pull-up/Pull-down: `No pull`
- User Label: `TILT_SENSOR`

The SW-520D module already includes an LM393 comparator and an output pull-up resistor, so the STM32 internal pull-up or pull-down resistor is normally not required.

### BUZZER

- Mode: `GPIO_Output`
- Output type: `Push-Pull`
- Pull-up/Pull-down: `No pull`
- Speed: `Low`
- User Label: `BUZZER`

## Module indicators

The SW-520D module has two indicator LEDs:

- `PWR-LED`: turns on when the module is powered.
- `DO-LED`: indicates the digital output state.

The tested module behaves as follows:

| Mechanical switch | DO output | DO LED |
| ----------------- | --------- | ------ |
| Open              | High      | Off    |
| Closed            | Low       | On     |

Therefore, the module is active-low:

```text
DO = GPIO_PIN_RESET -> triggered
DO = GPIO_PIN_SET   -> not triggered
```
