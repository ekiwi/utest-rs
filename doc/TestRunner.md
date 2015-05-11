# Test Runner

One component of a unit test library for deeply embedded, bare metal
targets needs to be a test runner. This component runs on the
host computer and manages access to the target as well as the collection
and representation of results.

## Tasks
* load test onto the target
* start test on target
* collect results from target
* load next test
* eventually report results

## Requirements
* provide a way to load code onto the micro controller
* provide a way to receive test results 
* interact with `rustc` to find out which tests have to be run
* maybe give maximum size hints to `rustc` in order to be able
  to decide how many test cases to compile into one binary
* customizable for different micro controller setups (see below)

## Ways to Load Code Onto the Target
* JTAG/SWD adapter connected via USB (e.g. trough `openocd`)
* UART/CAN/SPI/I2C adapter connected via USB and boot loader
  on the target

## Ways to Communicate With the Target
* JTAG/SWD read access to memory region
* UART output (often through USB [serial device](https://crates.io/crates/serial))
* CAN/SPI/I2C adapter (this is not the _norm_)
