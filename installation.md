Rust

低レイヤー向けにC/C++に取って代わると言われているプログラミング言語Rustが気になっている方も結構いらっしゃるのではないでしょうか？登場した当初は一時の流行りかと思ってそれほど気にしていなかったのですが、Linuxのカーネルの一部にRustが採用され始めたことから一気に気になる存在に昇格したのが去年の暮くらいだったでしょうか？低レイヤーの言語はC/C++を知っていれば対応できると長年に渡り思っていましたがC/C++では時代の要請に答えられなくなりつつあるのがどうやら現状のようです。この連載ではRust公式のプログラミング言語Rust（通称The Book）で筆者がRustで学んだ事項の覚書です。

Rustのインストールから基本的なシンタックスから始まり、データ型やオーナーシップ（所有権でいい？）などの基本的な事項から始まって、最後はマルチスレッドのWEBサーバーを作成までをカバーします。

Rustを勉強しながらハマったところ、つまずいたところ、注意したほうが良いところなどを各項目ごとにまとめて読みやすい連載形式でお届けする企画です。

本連載を通じて多くの方がRustの世界を楽しんでいただければ幸いでございます。



対象の方

ある程度他の言語でプログラミングの経験があることが望ましいです。

LinuxやmacOSなどのターミナルからコマンド操作を行えることを前提としています。

特定のIDEやエディタに依存した事項につきましては言及は可能な限り避けることとし、主にコマンドラインからRust標準のツール類を操作しながら学習を進めます。

テキストエディタは読者のお好みをエディタをご使用ください。



まず初めに環境整備から。

Rustをインストール

RustでHello World!

Rustのパッケージマネージャー兼ビルドシステムであるcargoについての説明



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
