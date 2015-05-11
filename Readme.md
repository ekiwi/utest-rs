# utest-rs

The goal of this repository is to develop a solution for running
standard rust unit tests on deeply embedded, bare metal targets.

See also [this issue](https://github.com/rust-lang/rfcs/issues/816#issuecomment-100377572).

## How can I collaborate?

Feel free to open issues and send in pull requests.

## Goals
* to develop a flexible testing harness and test runner that can
  be adjusted for different micro controller setups
* work out what needs to be change in `rustc`/`cargo` in order to
  integrate this with the regular rust workflow

## Constraints on Deeply Embedded, Bare Metal Targets
* only `libcore` available
* only `stack` no `heap` memory allocation
* restricted code size (common flash sizes are 128kB)
* no support for stack unwinding, thus no `panic`
* because of size constraints, stack unwinding might never be feasible
* `heap` allocation is not too hard to make work, it would just make this more
  universal, if we did not require it

## Test Harness
* does not allocate dynamic memory
* does not use panic
* returns compact error descriptions (maybe error numbers)
* makes it possible to split up tests into several binaries
  because one monolithic binary for all tests might not fit into program memory
* there might be a component running on the host pc, that loads the
  tests onto the micro controller and collects test results e.g. via USB
