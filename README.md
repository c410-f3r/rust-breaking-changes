I have lost count of a handful of breaking changes regarding the Rust programming language, threfore, this repository to remind me of what could be changed/removed from the language. If you know any topic that is not in the list, feel free to fill a PR.

Please, bare in mind that [rust-lang/rfcs#1105] explicitly state that no public API should be modified in a way that could break someone's code.

* `Vec::retain(...)` closure should receive `&mut T` instead of `&T`. E.g.: Both `ArrayVec` and `SmallVec` use `F: FnMut(&mut T) -> bool`. [#25477]

* Don't allow matching on floating-point literals. [#41255]

* This one is more like a personal preference: `Range`, `RangeFrom`, `RangeTo` and `RangeToInclusive` fields should be private. [#49022]

* The `IntoIterator` implementation for arrays should return owned values instead of references. [#65819]

* Remove `Infallible` for good and stabilize the never type `!`. [#66757], [#67224]

* Remove the `description` method from the `Error` trait. [#66919]

* Remove primitive numeric modules and associated functions. [#68490]

[rust-lang/rfcs#1105]: https://github.com/rust-lang/rfcs/pull/1105
[#25477]: https://github.com/rust-lang/rust/issues/25477 
[#41255]: https://github.com/rust-lang/rust/issues/41255
[#49022]: https://github.com/rust-lang/rust/issues/49022
[#65819]: https://github.com/rust-lang/rust/pull/65819
[#66757]: https://github.com/rust-lang/rust/issues/66757
[#66919]: https://github.com/rust-lang/rust/pull/66919/
[#67224]: https://github.com/rust-lang/rust/pull/67224
[#68490]: https://github.com/rust-lang/rust/issues/68490