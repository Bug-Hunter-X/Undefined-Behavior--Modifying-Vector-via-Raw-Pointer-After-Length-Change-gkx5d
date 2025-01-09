# Undefined Behavior in Rust: Modifying Vector via Raw Pointer

This repository demonstrates a common source of undefined behavior in Rust: modifying a vector through a raw pointer after the vector's length or capacity has changed.  The `bug.rs` file contains the erroneous code, while `bugSolution.rs` presents a safe and correct alternative.

## Problem
The issue lies in directly manipulating memory using `as_mut_ptr()` without proper handling of potential changes to the vector's underlying allocation.  This practice violates Rust's memory safety guarantees and may result in data corruption, panics, or crashes.

## Solution
The solution involves avoiding direct memory manipulation using raw pointers.  Instead, use safe Rust's built-in methods to modify the vector's contents.