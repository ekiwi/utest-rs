# Compiling Rust for Microcontrollers

Right now there are several efferts underway to run `rust` programs
on (ARM cortex-m based) microcontrollers.

* [antoinealb/rust-demo-cortex-m4](https://github.com/antoinealb/rust-demo-cortex-m4)
  links rustc code with c, uses `make`, [blog post](http://antoinealb.net/programming/2015/05/01/rust-on-arm-microcontroller.html)
* [hackndev/zinc](https://github.com/hackndev/zinc) is the `pure` rust
  approach to micro controllers, currently using a ruby build system,
  but [planning to switch to cargo](https://github.com/hackndev/zinc/pull/219)
  has been [a little bit inactive lately](https://github.com/hackndev/zinc/issues/284)
* [neykov/armboot](https://github.com/neykov/armboot) was one of the earliest
  efforts to run rust on micro controllers, uses `make` does not work
  with the latest `rustc`
* [dpc/titanos](https://github.com/dpc/titanos) is an OS for bare metal ARMv8,
  is not targeted at micro controllers, but probably the bare metal project
  with the best `cargo` support right now
