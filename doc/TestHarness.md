# Test Harness

This is the component running on the micro controller. Basically, the goal
here is to reimplement the rust unit test API, namely
[libtest](https://github.com/rust-lang/rust/tree/master/src/libtest),
in a way that makes it possible to run on a micro controller.

## Constraints
* may not use panic, as stack unwinding might be impossible,
  or very impractical on highly memory constraint devices
* should not use dynamic heap allocation in order to make it
  easier to port
* should only use libcore

## Ideas
* could use error numbers instead if strings, the test runner can
  then replace these with the corresponding string on the host computer,
  thus saving bandwidth and program memory
* we could build the test harness as a static library and require
  some external symbols in order to send data to the test runner on
  the host computer, everything else should be pretty generic
