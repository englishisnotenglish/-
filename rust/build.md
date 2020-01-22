# Rust 构建

- A:安装

   安装遵从官网的教程

- B: Cargo 构建 hello world，了解Cargo的基本使用和Rust程序的构建和启动

  1.[卡狗官方教程](https://doc.rust-lang.org/cargo/getting-started/first-steps.html)
  
  2.构建的过程中，缺失c++库，看来rust底层依赖c++，
  [can't find link.exe](https://stackoverflow.com/questions/55603111/unable-to-compile-rust-hello-world-on-windows-linker-link-exe-not-found) 安装好c++工具库就构建成功。
      
      2.1 以后一定要记住构建一定有存在前置依赖的，构建失败一般都是缺失前置库依赖。

   3.构建成功后在debug里面的生成项目名称。访问./target/debug/xxx可以直接运行
   
      3.1.可以直接run cargo run

   4.总结一下还是类c，程序的入口还是main函数