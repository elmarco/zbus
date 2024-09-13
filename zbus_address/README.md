# zbus_address

[![](https://docs.rs/zbus_address/badge.svg)](https://docs.rs/zbus_address/) [![](https://img.shields.io/crates/v/zbus_address)](https://crates.io/crates/zbus_address)

Handle [D-Bus server addresses][dba] parsing.

This is used by [`zbus`]. Other D-Bus crates are also encouraged to use this API in the spirit of cooperation. :)

For convenience, `zbus` re-exports this crate as `address`, so you do not need to depend directly on
this crate if you already depend on `zbus`.

# Miscellaneous and caveats on D-Bus addresses

* Assumes values are UTF-8 encoded: this should be clarified in the spec
  otherwise, fail to read them or use a lossy representation for display.

* Assumes that empty `key=val` is accepted, so `transport:,,guid=...` is valid.

* Allows key only, so `transport:foo,bar` is ok.

* Accept unknown keys and transports.

**Status:** Stable.

[`zbus`]: https://crates.io/crates/zbus
[`zbus_macros`]: https://crates.io/crates/zbus_macros
[dba]: https://dbus.freedesktop.org/doc/dbus-specification.html#addresses
