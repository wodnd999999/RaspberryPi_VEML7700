# RaspberryPi-VEML7700
RaspberryPi driver for VEML7700 ambient light sensor. This is ported from tedyapo/arduino-VEML7700 which is available in Arduino.

# Connections
The VEML7700 uses I2C communication.  Connect it to the RaspberryPi SCL and SDA pins.

# Usage
see examples/read_VEML7700 for a simple example (not modifiied yet. this file is for arduino. but similar usage.)

# API
The code exposes a low-level set of API functions corresponding to the command set described in the datasheet and a higher-level API for ease of use

## High-level API

    uint8_t VEML7700::getALSLux(float& lux);
samples the current ambient light value (photopic curve) using the current gain and integration time settings. Returns 0 on success, non-zero on failure.

    uint8_t VEML7700::getWhiteLux(float& lux);
samples the current ambient light value (white-like curve) using the current gain and integration time settings. Returns 0 on success, non-zero on failure.

    uint8_t VEML7700::getAutoALSLux(float& lux);
samples the current ambient light value (photopic curve) using auto-ranging algorithm described in application note. Returns 0 on success, non-zero on failure.

    uint8_t VEML7700::getAutoWhiteLux(float& lux);
samples the current ambient light value (white-like curve) using auto-ranging algorithm described in application note. Returns 0 on success, non-zero on failure.

    void VEML7700::sampleDelay();
delays (busy-wait) long enough to ensure a new sample is generated after the call is executed, based on current setting of integration time.
