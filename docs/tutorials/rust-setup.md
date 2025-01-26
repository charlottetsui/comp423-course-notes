# Setting up a Dev Container for Rust

* Primary author: [Charlotte Tsui](https://github.com/charlottetsui/comp423-course-notes)

<!-- Tutorial Content Requirements
Your tutorials should include:

Prerequisites
Step-by-step instructions for creating a new Dev Container project for your language
Should start from a blank directory and include git initialization
Dev Container configuration file explanations
Steps to create a new project, write a basic "Hello COMP423" program, compile, and run
The program's requirement is that it simply prints "Hello COMP423" out to standard output
Make use of Material for MkDocs features to enhance your documentation:

Code blocks with syntax highlighting for configuration files and commands
Admonitions for important notes and warnings
You can cite and reuse instructions from the 423 MkDocs tutorial if useful. -->

## Prerequisites
Please make sure you have the following before continuing

- [Git](https://git-scm.com/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Docker](https://www.docker.com/)

## Step 1: Create a Blank Directory and Initialize Git
1. Open your terminal and create a new directory for your project.

```bash
mkdir comp423-rust-setup 
cd comp423-rust-setup
```
2. Initialize a new Git repository.

```bash
git init
```

## Step 2: Development Container Configuration
1. In VS Code, open the newly created `comp423-rust-setup` directory
2. Inside the project, create a new `.devcontainer` directory in the root of your project history with the following file inside of this "hidden" configuraiton directory:
`.devcontainer/devcontainer.json`
3. Open `devcontainer.json` and configure the development environment and shown below:
```
{
  "name": "Rust Setup",
  "image": "mcr.microsoft.com/vscode/devcontainers/rust:1",
  "customizations": {
    "vscode": {
      "settings": {},
      "extensions": ["rust-lang.rust-analyzer", "matklad.rust-analyzer" ],
      "postCreateCommand": "rustup update && ruste --version"
    }
  } 
}
```

## Step 3: Reopen in Dev Container
Reopen the project in your dev container by pressing `Ctrl+Shift+P` or `Cmd+Shift+P` on Mac. Type in "Dev Containers: Reopen in Container" and wait for your container setup to complete.

## Step 4: Create a new Rust Project
1. In a new terminal, type the following:
```bash
cargo new hello_comp423
```
2. Navigate to your project directory.
```bash
cd hello_comp423
```
3. Write your simple program!
```rust
fn main() {
    println!("Hello, COMP423!");
}
```

## Step 5: Build and Run your Project
1. Build your project using **Cargo**. Open a new VS Code terminal and type:
```bash
cargo build
```
2. Run your project using Cargo
```bash
cargo run
```
## Expected output
```bash
Hello COMP423!
```

!!! info Uninstall Rust
      If at any point you need to uninstall Rust, run the command `rustup self uninstall`.