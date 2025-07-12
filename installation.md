~ ❯❯❯ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh  
info: downloading installer  

Welcome to Rust!  

This will download and install the official compiler for the Rust  
programming language, and its package manager, Cargo.  

Rustup metadata and toolchains will be installed into the Rustup  
home directory, located at:  

 /home/detomasomodena/.rustup  

This can be modified with the RUSTUP_HOME environment variable.  

The Cargo home directory is located at:  

 /home/detomasomodena/.cargo  

This can be modified with the CARGO_HOME environment variable.  

The cargo, rustc, rustup and other commands will be added to  
Cargo's bin directory, located at:  

 /home/detomasomodena/.cargo/bin  

This path will then be added to your PATH environment variable by  
modifying the profile files located at:  

 /home/detomasomodena/.profile  
 /home/detomasomodena/.bash_profile  
 /home/detomasomodena/.bashrc  
 /home/detomasomodena/.zshenv  

You can uninstall at any time with rustup self uninstall and  
these changes will be reverted.  

Current installation options:  

  default host triple: x86_64-unknown-linux-gnu  
    default toolchain: stable (default)  
              profile: default  
 modify PATH variable: yes  

1) Proceed with standard installation (default - just press enter)  
2) Customize installation  
3) Cancel installation  
   
   > 

info: profile set to 'default'  
info: default host triple is x86_64-unknown-linux-gnu  
info: syncing channel updates for 'stable-x86_64-unknown-linux-gnu'  
info: latest update on 2025-06-26, rust version 1.88.0 (6b00bc388 2025-06-23)  
info: downloading component 'cargo'  
info: downloading component 'clippy'  
info: downloading component 'rust-docs'  
info: downloading component 'rust-std'  
info: downloading component 'rustc'  
76.3 MiB /  76.3 MiB (100 %)  33.7 MiB/s in  2s            
info: downloading component 'rustfmt'  
info: installing component 'cargo'  
info: installing component 'clippy'  
info: installing component 'rust-docs'  
info: installing component 'rust-std'  
29.5 MiB /  29.5 MiB (100 %)  26.7 MiB/s in  1s            
info: installing component 'rustc'  
76.3 MiB /  76.3 MiB (100 %)  29.3 MiB/s in  2s            
info: installing component 'rustfmt'  
info: default toolchain set to 'stable-x86_64-unknown-linux-gnu'  

 stable-x86_64-unknown-linux-gnu installed - rustc 1.88.0 (6b00bc388 2025-06-23)  

Rust is installed now. Great!  

To get started you may need to restart your current shell.  
This would reload your PATH environment variable to include  
Cargo's bin directory ($HOME/.cargo/bin).  

To configure your current shell, you need to source  
the corresponding env file under $HOME/.cargo.  

This is usually done by running one of the following (note the leading DOT):  
. "$HOME/.cargo/env"            # For sh/bash/zsh/ash/dash/pdksh  
source "$HOME/.cargo/env.fish"  # For fish  
source $"($nu.home-path)/.cargo/env.nu"  # For nushell  
~ ❯❯❯

rustc --version  
rustc 1.88.0 (6b00bc388 2025-06-23)  
~ ❯❯❯



 まずはインストールしてみる。

インストールチェックしてHello World , Hello Cargo


