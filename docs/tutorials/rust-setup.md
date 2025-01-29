# Let's set up a dev container in Rust!

* Primary author: [Richard Tan](https://github.com/richatan1)
* Reviewer: [Daniel Zhang](https://github.com/d123aniel)

## Rust Introduction: 

Rust is a modern programming language created in 2012 to help creating more reliable software. It helps you write faster and control low-level details without many the traditional hassles you can think of. 

## Installs

*1. Install [VS Code](https://code.visualstudio.com/download)*
*2. Install [Git](https://git-scm.com/downloads)*
*3. Install [Docker](https://www.docker.com/get-started/)*


## Steps
1. On your machine, create a folder in your linux terminal: 

> `mkdir RustExample`
> `cd RustExample`

    To initialize a new git repository, use 'git init'. Follow the following code to make a README file in the new repository:

> `echo "# Rust Hello World Example by Richard" > README.md`
> `git add README.md`
> `git commit -m "README commit"`


2. Use File -> Open to the files in VSCode.
3. Create a folder named ".devcontainer" and add a devcontainer.json file in it. Include the following:
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
    _The new dev container .json file tells the container what needs to be setup. In this file, you give it a name (RustExample), install the latest image of Rust, and add a rust analyzer extension_

4. In the .json file, press Ctrl+Shift+P and select option "Dev Containers: Rebuild & Reopen Container( _Docker must be running for this to work._)

5. When the dev container opens, launch a terminal and use `rustc --version` to check if you have currently installed latest version of Rust

6. Run  `cargo new hello --vcs none`. This creates a new hello folder in your container.

7. Switch to the new hello folder `cd hello`, go to src -> main.rs file. Edit to the following code:
```Rust
fn main() {
    println!("Hello, COMP423!");
}
```

8. Run ```cargo build```. 
9. Run ```./target/debug/hello``` to execute the file. If everything works successfully, you should see this: 
```Rust
Hello, COMP423!
```
If not, return to main.rs file and double-check your code.
10. You can also use ```cargo run``` from the hello subdirectory to compile and run the program in 1 step  

### Side Note: 
    _`run` compiles and executes the program immediately, while `build` compiles but doesn't execute the program. Instead, a binary executable file is created to be executed independently._


##  Closing Note: When finished, don't forget your files using Git commands. Thank you for following along!