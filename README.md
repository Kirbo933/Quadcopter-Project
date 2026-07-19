# Quadcopter-Project
Custom quadcopter with gesture control and an independent sensor-logging payload.


# Instrumented Quadcopter

A quadcopter I'm building from scratch this summer. Two things make it
different from a normal drone build: I control it with a glove instead of
a stick, and it carries its own sensor payload that logs flight data so I
can compare how different altitude sensors disagree in the air.

## The idea

Three sensors can tell you how high a drone is: a barometer, a laser
rangefinder, and GPS. They all give different answers, and they're each
wrong in their own way. The barometer drifts, the laser only works close
to the ground, GPS altitude is noisy. The main experiment here is flying
all three at once, logging them, and figuring out which one to trust and
when.

The flight side runs on its own so it's not tangled up with the logging.
Betaflight flies the drone. A separate microcontroller only read sensors
and write to an SD card, so if the logger dies mid-flight the
drone stays up.

## Status

Just started (summer 2026). Parts are on the way. Right now this is mostly
structure and notes. It'll fill in as I build.

## What's in here

- `firmware-logger/` - the sensor datalogger, runs on a Teensy 4.1
- `firmware-glove/` - the glove controller, runs on an ESP32
- `analysis/` — Python for reading the logs and making plots
- `cad/` - the frame, designed in Fusion 360
- `docs/` - build log, wiring, and notes

## Hardware

Full parts list is in `docs/`. The short version: a 5" quad on a SpeedyBee
F405 stack, four 2207 motors, ExpressLRS radio, and the sensor payload
(BME280 barometer, VL53L1X laser rangefinder, BN-880 GPS).

[Full parts list](docs/parts.md)

## Results

Coming once it flies. This is where the sensor comparison plots, the FEA on
the frame, and the flight data will go.

## License

Code is MIT. CAD files are CC-BY-4.0.
