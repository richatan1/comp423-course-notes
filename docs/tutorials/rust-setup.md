# Setting up a dev container for Rust

* Primary author: [Richard Tan](https://github.com/richatan1)
* Reviewer: [Daniel Zhang](https://github.com/d123aniel)

## Rust

Created in 2012, Rust is a modern programming language used to create reliable software.

## Pre-requisites
### Installs

1. Install [VS Code](https://code.visualstudio.com/download)
2. Install [Git](https://git-scm.com/downloads)
3. Install [Docker](https://www.docker.com/get-started/)


### Steps
1. On a folder on your machine, create a folder using the terminal
```
mkdir RustExample
cd RustExample
```

    Use ```git init``` to initialize a git repository. Use this to create a README:
```
echo "# Rust Hello World Example by Richard" > README.md
git add README.md
git commit -m "README commit"
```

2. Open this folder in VS Code
3. Create a folder named ".devcontainer" (for simplicity) and add a devcontainer.json file in it. Include the following:
```
{
    "name": "RustExample",
    "image": "mcr.microsoft.com/vscode/devcontainers/rust:latest",
    "customizations": {
      "extensions": ["rust-lang.rust-analyzer"]
    }
}
```
Explanation: 
    Your dev container .json file communicates to the container what needs to be setup. In this file, you give it a name (RustExample), install the latest image of Rust, and add a rust analyzer extension

4. In the .json file, press Ctrl+Shift+P and select option "Dev Containers: Rebuild & Reopen Container (just rebuild container is fine too). This might take a minute. (**Not working?** Ensure Docker is running)

5. Once container starts, open a terminal and use the following to ensure you have the most [recent](https://releases.rs/) version of Rust
```
rustc --version
```
6. In the terminal, run the following ```cargo new hello --vcs none```.

7. In the newly created hello folder (cd hello), go to src --> main.rs file (Rust extension is .rs). Edit to the following code:
```Rust
fn main() {
    println!("Hello, COMP423!");
}
```

8. cd into the newly made hello folder, run ```cargo build```
9. Use ```./target/debug/hello``` to run the file. You should see this in the terminal
```Rust
Hello, COMP423!
```
If you don't see this, go back to main.rs file and ensure the code is correct
10. You can also use ```cargo run``` from the hello subdirectory to compile and run the program in 1 step  

Explanation: "build vs run"
while ```cargo build``` only compiles the project but doesn't actually run it (you have to do it manually as seen above), ```cargo run``` does both

**### When finished with the project, go back using ```cd ..``` and use ```git add .``` & ```git commit -m ""``` to log your files using Git**

# Thank you for following along!