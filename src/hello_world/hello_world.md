# hello_world.rs
In the [hello_world.rs](https://github.com/Polycarbohydrate/small-rust-binary/blob/main/src/hello_world/hello_world.rs) file, there is code to print `Hello World` to `stdout`. We use the [`println!`](https://doc.rust-lang.org/std/macro.println.html) macro to do this.

```rust
fn main(){println!("Hello, world!");}
```

There is only one space in this line of code separating the function, `fn`, call and the name of the function, `main`. Everything is kept to one line and no unnecessary spaces are used to minimize the binary size just from the code.

### Building with defaults
When running the command `cargo build` the file compiles to a size of `~141` kilobytes (`144,384` bytes).

![Screenshot 2025-04-15 175742](https://github.com/user-attachments/assets/ba4fd767-0f0c-4784-be9a-ec3e41226e89)

*Figure 1: `small-rust-binary\target\debug\small-rust-binary.exe` built by `cargo build`*

### Building in release mode
When running the command `cargo build --release` the file compiles to a size of `~137` kilobytes (`140,800` bytes).

![Screenshot 2025-04-15 182056](https://github.com/user-attachments/assets/c67996ee-2d84-45af-933e-08292d839110)

*Figure 2: `small-rust-binary\target\release\small-rust-binary.exe` built by `cargo build --release`*

Reduction of `3,584` bytes from default build.

### Building with strip enabled
Since this testing is done on Windows, the strip command does nothing to the file size. The file size is the same as in Figure 2. Neverless, the option is still avaiable in the associated cargo.toml file.

### Building with opt-level 's'
Same exact size as building in *Figure 2*. Option is still included in the Cargo.toml file.

### Building with opt-level 'z'
Same exact size as building in *Figure 2*. Option is still included in the Cargo.toml file.

### Building with link time optimization enabled
When running the command `cargo build --release` and the having the Cargo.toml file include:

```toml
[profile.release]
lto = true
```

the build size drops dramatically to `124` kilobytes (`126,976` bytes).

![Screenshot 2025-04-16 164916](https://github.com/user-attachments/assets/676e895b-5d31-46fc-94df-14496c138744)

Reduction of `17,408` bytes from the default build *(Figure 1)*.
Reduction of `13,824` bytes from the initial release build *(Figure 2)*.

#### Variables
Rustc version: `1.86.0`

Channel: `stable-x86_64-pc-windows-msvc`

Cargo version: `1.86.0`

IDE: [`RustRover`](https://www.jetbrains.com/rust/)

RustRover version: `2024.3.8`

RustRover build: `243.26053.64`

JetBrainsRuntime version: `21.0.6b631.39`
