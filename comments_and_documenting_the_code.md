# Comments and Documenting the code

```
// Line comments
/* Block comments */
```

Nested block comments are supported.

💡 **Always avoid block comments, Use line comments instead.**

```
/// Line comments; document the next item
/** Block comments; document the next item */

//! Line comments; document the enclosing item
/*! Block comments; document the enclosing item !*/
```

Doc comments support Markdown notations. Using ```cargo doc```, the HTML documentation can be generated from these doc comments. Let’s see the difference between the two sets of doc comments.

```
/// This module contains tests
mod test {
    // ...
}


mod test {
    //! This module contains tests

    // ...
}
```

As you can see both use to document the same module. First comment has been added before the module while the second one has been added inside the module.

💡 **Only use //! to write crate and module-level documentation, nothing else. When using mod blocks, use /// outside of the block.**

Also we can use **doc attributes** for documenting the code.

> 🔎An [attribute](https://doc.rust-lang.org/reference.html#attributes) is a general, free-form **metadatum** that is interpreted according to name, convention, and language and compiler version. Any item declaration may have an attribute applied to it. 

In here each comments are equivalent to relevant data attributes.

```
/// Foo
#[doc="Foo"]

//! Foo
#![doc="Foo"]
```