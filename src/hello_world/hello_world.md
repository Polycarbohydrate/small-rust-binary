# hello_world.rs
In the [hello_world.rs](https://github.com/Polycarbohydrate/small-rust-binary/blob/main/src/hello_world/hello_world.rs) file, there is code to print `Hello World` to `stdout`. We use the [`println!`](https://doc.rust-lang.org/std/macro.println.html) macro to do this.

There is only one space in this line of code separating the function, `fn`, call and the name of the function, `main`. Everything is kept to one line and no unnecessary spaces are used to minimize the binary size just from the code.

### Compiling with defaults
When running the command ```cargo build``` the file compiles to a size of `~141` kilobytes (`144384` bytes).

![Screenshot 2025-04-15 175742](https://github.com/user-attachments/assets/ba4fd767-0f0c-4784-be9a-ec3e41226e89)


#### Variables
Rustc version: `1.86.0`

Channel: `stable-x86_64-pc-windows-msvc`

Cargo version: `1.86.0`

IDE: [`RustRover`](https://www.jetbrains.com/rust/)

RustRover version: `2024.3.8`

RustRover build: `243.26053.64`

JetBrainsRuntime version: `21.0.6b631.39`
