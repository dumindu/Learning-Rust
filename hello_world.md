# Hello World

```
fn main() {
    println!("Hello, world!");
}
```

```fn``` means function. main function is the beginning of every Rust program.  
```println!``` prints text to the console and its *!* indicate that it’s a [macro](https://doc.rust-lang.org/book/macros.html) instead of a function.

> 💡 Rust files should have .rs file extension and if you’re using more than one word for the file name, follow the [snake_case](https://en.wikipedia.org/wiki/Snake_case).

compiling via ```rustc file.rs```  
executing by ```./file``` on Linux and Mac or ```file.exe``` on Windows