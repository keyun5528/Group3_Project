# Rust vs. C/C++ — Key Developments & How It Works

**Presenter:** Ridwan Alabi  
**Estimated speaking time:** Approximately 2 minutes

## Slide 1: Key Developments

Thank you, Keyun. I'll explain how Rust developed and how it improves memory safety.

Rust was officially released in 2015. Unlike C and C++, where programmers often manage memory manually, Rust helps prevent memory errors automatically. In 2022, Rust support was introduced into the Linux kernel, showing its growing importance.

## Slide 2: How Rust Works

Rust uses three important concepts: **ownership, borrowing, and the borrow checker**.

Ownership means every value has an owner. Borrowing allows another part of the program to use that value temporarily. The borrow checker checks these rules before the program runs, helping prevent memory errors.

## Slide 3: Rust vs. C/C++

In C and C++, programmers can accidentally access memory after it has been released. This is called a use-after-free error.

Rust uses ownership rules to prevent many of these mistakes during compilation, making programs safer.

## Slide 4: Borrowing Rules

Rust allows multiple references to read data, or one reference to modify it, without conflicting access.

The compiler checks these rules to prevent unsafe memory operations.

## Slide 5: Industry Shift

Companies are increasingly interested in Rust because it combines performance with memory safety.

It can prevent many common programming errors without requiring a garbage collector.

Rust does not completely replace C or C++, but it offers a safer option for developing new software.

**That concludes my section. I'll now hand over to Muhammed, who will explain the impact of Rust on software development. Thank you.**
