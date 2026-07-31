# STM32 Experiments

A collection of STM32 learning projects and peripheral experiments.

## Hardware

- Development board: NUCLEO-F446RE
- Microcontroller: STM32F446RE
- Debugger: On-board ST-LINK/V2-1

## Development Environment

- STM32CubeIDE
- STM32CubeMX
- STM32CubeF4
- C language

## Repository Structure

Each folder contains an independent STM32CubeIDE project.

```text
stm32-experiments/
├── 01_gpio/
│   ├── 01_led_blink/
│   ├── 02_led_running/
│   ├── 03_button_polling/
│   └── 04_buzzer_and_sensor/
│
├── 02_exti_nvic/
│   ├── 01_button_exti/
│   ├── 02_interrupt_priority/
│   └── 03_encoder_exti/
│
├── 03_usart/
│   ├── 01_uart_polling/
│   ├── 02_uart_interrupt/
│   ├── 03_uart_packet/
│   ├── 04_printf_redirect/
│   └── 05_uart_dma/
│
├── 04_timers/
│   ├── 01_systick_delay/
│   ├── 02_basic_timer_interrupt/
│   ├── 03_pwm_breathing_led/
│   ├── 04_pwm_servo/
│   ├── 05_pwm_dc_motor/
│   ├── 06_input_capture/
│   ├── 07_pwm_input/
│   ├── 08_encoder_interface/
│   └── 09_advanced_timer/
│
├── 05_adc_dac/
│   ├── 01_adc_single_channel/
│   ├── 02_adc_multi_channel/
│   ├── 03_adc_dma/
│   └── 04_dac_output/
│
├── 06_dma/
│   ├── 01_memory_transfer/
│   ├── 02_uart_tx_dma/
│   └── 03_peripheral_transfer/
│
├── 07_i2c/
│   ├── 01_software_i2c_eeprom/
│   ├── 02_hardware_i2c_eeprom/
│   └── 03_mpu6050/
│
├── 08_spi_qspi/
│   ├── 01_software_spi_flash/
│   ├── 02_hardware_spi_flash/
│   ├── 03_w25qxx_driver/
│   └── 04_qspi_flash/
│
├── 09_internal_memory/
│   ├── 01_device_id/
│   ├── 02_internal_flash/
│   └── 03_persistent_settings/
│
├── 10_external_memory/
│   ├── 01_fmc_pin_feasibility/
│   ├── 02_external_sram/
│   └── 03_sram_test/
│
├── 11_display/
│   ├── 01_oled_i2c/
│   ├── 02_spi_lcd/
│   ├── 03_parallel_lcd/
│   └── 04_graphics_primitives/
│
├── 12_can/
│   ├── 01_can_loopback/
│   ├── 02_can_interrupt/
│   └── 03_can_dual_node/
│
├── 13_rtc_power/
│   ├── 01_backup_register/
│   ├── 02_rtc_clock/
│   ├── 03_rtc_alarm/
│   ├── 04_sleep_mode/
│   ├── 05_stop_mode/
│   └── 06_standby_mode/
│
├── 14_watchdog/
│   ├── 01_iwdg/
│   └── 02_wwdg/
│
├── 15_usb_sdio/
│   ├── 01_usb_device/
│   ├── 02_usb_cdc/
│   └── 03_sdio_sdcard/
│
├── 16_ethernet/
│   ├── 01_w5500_basic/
│   ├── 02_w5500_tcp_udp/
│   └── 03_w5500_web_server/
│
├── 17_wireless/
│   ├── 01_esp32c3_wifi_at/
│   ├── 02_bluetooth_uart/
│   └── 03_lora_node_gateway/
│
└── 18_integrated_projects/
    ├── 01_uart_configurable_running_led/
    ├── 02_mpu6050_display_dashboard/
    ├── 03_adc_dma_oscilloscope/
    ├── 04_rtc_alarm_low_power/
    └── 05_sensor_data_logger/
```
