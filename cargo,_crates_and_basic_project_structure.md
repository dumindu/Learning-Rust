# Cargo, Crates and Basic Project Structure

Cargo is Rust’s build-in Package Manager. But mainly it uses for,  

01 Create new project : ```cargo new```  
02 Update dependencies : ```cargo update```  
03 Build project : ```cargo build```  
04 Build and run a project : ```cargo run```  
05 Run tests : ```cargo test```  
06 Generate documentation via rustdoc : ```cargo doc```  

Other than that there are some cargo commands, especially for publishing crates directly via cargo.

07 ```cargo login``` : acquiring an API token  
08 ```cargo package``` : make the local create uploadable to crates.io  
09 ```cargo publish``` : make the local create uploadable to crates.io and upload the crate  

🌟 **A crate is a package. Crates can be shared via [Cargo](https://crates.io/).**

A crate can produce an executable or a library. In other words, it can be a binary crate or a library crate.  
```cargo new crate_name --bin``` : produces an executable  
```cargo new crate_name (--lib)```: produces a library  

The first one will generate,
```
├── Cargo.toml
└── src
    └── main.rs
```

and the second one will generate,

```
├── Cargo.toml
└── src
    └── lib.rs
```

* **Cargo.toml**(capital c) is the configuration file which contains all of the metadata that Cargo needs to compile your project.
* **src** folder is the place to store the source code.  
* Each crate has an implicit crate root/ entry point. **main.rs** is the crate root for a binary crate and **lib.rs** is the crate root for a library crate. 

💡 When we build a binary crate via ```cargo build``` or ```cargo run```, the executable file will be stored in **target/debug/** folder. But when build it via **cargo build --release** for a release it will be stored in **target/release/** folder. 

> 🌟 However when the code base getting larger, we can divide multiple file creates into modules. We can load modules via ```mod``` keyword from main.rs/lib.rs.  
For example: when using mod in the main.rs, it checks <module_name>.rs on project’s src folder or mod.rs on module root. However using mod.rs is the best practice.