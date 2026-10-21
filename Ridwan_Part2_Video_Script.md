# Rust vs. C/C++ — The Industry Shift Toward Memory Safety
## Part 2: Key Developments & How It Works
**Presenter:** Ridwan Alabi  
**Estimated speaking time:** 4–5 minutes

### Slide 1 — Why memory safety became a priority
Thank you, Keyun, for the introduction. I will now explain the key developments behind Rust and how its memory-safety features work.

C and C++ are powerful programming languages, but they give programmers a lot of responsibility for managing memory. A mistake, such as accessing memory after it has been freed, can cause a crash or a security vulnerability.

Rust was developed to help prevent these kinds of errors without giving up the speed needed for systems programming. Work on Rust began in 2006, and version 1.0 was released in 2015. Another important milestone came in 2022, when support for Rust was added to the Linux kernel. This did not replace C, but it made Rust an option for some new kernel components.

### Slide 2 — Rust’s three core safety rules
So, how does Rust work?

The first idea is **ownership**. In Rust, every value has an owner. When the owner goes out of scope, Rust automatically cleans up the value. This avoids many mistakes associated with manual memory management.

The second idea is **borrowing**. Borrowing lets another part of the program use a value temporarily without taking ownership of it.

The third idea is the **borrow checker**. This is part of Rust's compiler. It checks whether references are valid and whether code follows Rust's borrowing rules. Many mistakes are caught before the program can run.

### Slide 3 — C/C++ and Rust: a simple example
Here is a simple comparison.

On the left, the C program allocates memory and then frees it. After that, it tries to write through the same pointer. This is called a **use-after-free** error. The code may compile, but accessing that memory is invalid and can lead to unpredictable behaviour.

On the right, the Rust example creates a string and moves its ownership to a new variable. If the program then tries to use the old variable, the compiler reports an error. The examples are not identical, but they show an important difference: Rust tracks ownership and stops certain unsafe operations during compilation.

### Slide 4 — What the compiler actually checks
Rust also controls how references are used.

A simple way to remember the rule is: you can have multiple readers, or one writer, but not conflicting access at the same time.

In this example, we first borrow a string to read it. After that borrow is no longer used, we can take a mutable reference to change it. Rust analyzes where references are used, so it can allow safe code and reject conflicting borrows.

This is especially valuable in large programs, where memory mistakes can be difficult to find through testing alone.

### Slide 5 — Why the shift matters
These developments explain why Rust is getting attention.

First, it can catch many memory-safety problems earlier, during compilation. Second, Rust is designed for high performance without requiring a traditional garbage collector. Third, companies do not have to rewrite all their existing C and C++ code. They can start using Rust in selected new components.

However, Rust is not a guarantee that every program is secure, and unsafe Rust code or external dependencies can still introduce risks.

That brings us to the next section. Muhammed will explain the impact of this shift on software development. Thank you.

---

## References
- Rust Programming Language, *The Rust Book*: https://doc.rust-lang.org/book/
- Rust Project, *Rust 1.0 Announcement*: https://blog.rust-lang.org/2015/05/15/Rust-1.0/
- Linux Kernel Documentation, *Rust*: https://docs.kernel.org/rust/
- CISA, *The Case for Memory Safe Roadmaps*: https://www.cisa.gov/resources-tools/resources/case-memory-safe-roadmaps
