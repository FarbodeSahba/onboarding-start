## How it works

This Tiny Tapeout onboarding project connects a PWM peripheral to the Tiny Tapeout top-level interface. The design uses control signals and registers to enable output pins and control PWM behavior.

The PWM peripheral drives the output pins through the combined output bus made from `uo_out` and `uio_out`. The `uio` pins are configured as outputs using `uio_oe = 8'hFF`.

The design includes output enable registers, PWM enable registers, and an 8-bit PWM duty cycle signal.

### Features

- Tiny Tapeout-compatible top module
- PWM peripheral integration
- 16 output signals using `uo_out[7:0]` and `uio_out[7:0]`
- 8-bit PWM duty cycle control
- `uio` pins configured as outputs

### Register map

| Signal | Description |
|---|---|
| `en_reg_out_7_0` | Enables output pins 7 through 0 |
| `en_reg_out_15_8` | Enables output pins 15 through 8 |
| `en_reg_pwm_7_0` | Enables PWM mode for output pins 7 through 0 |
| `en_reg_pwm_15_8` | Enables PWM mode for output pins 15 through 8 |
| `pwm_duty_cycle` | Sets the PWM duty cycle |

## How to test

The design can be tested using the Cocotb testbench in the `test/` directory.

From the repository root, run:

```bash
cd test
make