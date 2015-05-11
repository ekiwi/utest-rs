# Compiling Rust for Microcontrollers

Right now there are several efferts underway to run `rust` programs
on (ARM cortex-m based) microcontrollers.

* [antoinealb/rust-demo-cortex-m4](https://github.com/antoinealb/rust-demo-cortex-m4)
  links rustc code with c, uses Makefiles, [blog post](http://antoinealb.net/programming/2015/05/01/rust-on-arm-microcontroller.html)
* [hackndev/zinc](https://github.com/hackndev/zinc) is the `pure` rust
  approach to micro controllers, currently using a ruby build system,
  but [planning to switch to cargo](https://github.com/hackndev/zinc/pull/219)
  has been [a little bit inactive lately](https://github.com/hackndev/zinc/issues/284)
