---
tags:
  - rust
---
# First Reading
Structs and Enums are used to make custom types in rust.
??Trait Object
## Getting Started
### Installation
### Hello, World!
### Hello, Cargo!
## Programming a Guessing Game
By default, Rust has a set of items defined in the standard library that it brings into the scope of every program. This set is called the prelude, and you can see everything in it in the standard library documentation.

An associated function is a function that’s implemented on a type. It is denoted by :: .

Trait Vs Lib Vs Associated Functions Vs Method Syntax.

## Common Programming Concepts
### Variables and Mutability
Shadowing creates a new variable itself, so they can be different types
### Data Types
Lol, 2 types of strings.
### Control Flow
Using too many else if expressions can clutter your code, so if you have more than one, you might want to refactor your code. Chapter 6 describes a powerful Rust branching construct called match for these cases.

You can optionally specify a loop label on a loop that you can then use with break or continue to specify that those keywords apply to the labeled loop instead of the innermost loop. Loop labels must begin with a single quote.

```Rust
fn main() {
	for number in (1..4).rev() {
		println!("{number}!");
	}
	println!("Liftoff");
}
```


```Rust
fn main() {
	for number in (1..=4).rev() {
		println!("{number}!");
	}
	println!("Liftoff");
}
```
## Understanding Ownership
### What is Ownership
Rust has a special annotation called the `Copy` trait that we can place on types that are stored on the stack, as integers are. If a type implements the Copy trait, variables that use it do not move, but rather are trivially copied, making them still valid after assignment to another variable. 
Rust won't let us annotate a type with `Copy` if the type, or any of its parts, has implemented the `Drop` trait.
To learn about how to add the Copy annotation to your type to implement the trait, see “Derivable Traits” in Appendix C.
### References and Borrowing
Understand the differences between pointers and references.
### Slices
str literals are slices and hence are immutable references.
## Using Structs to Structure Related Data
All structs are owned.
### Defining and Instantiating Structs
#### Update Syntax
#### Tuple Structs
For typed Tuples like 
```Rust
struct Color(i32, i32, i32);
struct Point(i32, i32, i32);
```
#### Unit-Like Structs Without Any Fields
For types which need only traits but no data
```Rust
struct AlwaysEqual;
```
#### References inside Structs
Require the use of Lifetimes
### Method Syntax
#### Associated Functions
These are like constructors and are functions which do not use self and hence are not methods. Theses functions are namespaced by the struct: the `::` syntax is used for both associated functions and namespaces created by modules.
#### Multiple impl Blocks
These are useful for generic types and traits
## Enums and Pattern Matching
## Managing Growing Projects with Packages, Crates, and Modules
Packages Vs Crates Vs Modules and use Vs Paths
### Packages and Crates
Packages are like a collection of crates. Packages can have at most one library crate and many binary crates.
Crates are tree of modules.
### Defining Modules to Control Scope and Privacy
Modules are like ways to group similar functionality under a namespace and introduce public and private functionality into the system
### Paths for referring to an item in the module tree
Relative and Absolute paths
Private fields of a struct must have a public constructor
All variants of a pub enum are public.
### Bringing Paths into Scope with the use keyword
## Common Collections
First encounter of deref operator
### Vectors
Ez
### Strings
Complicated but doable
### HashMaps
## Error Handling
+ panic!
+ Result enum
? can't convert from Result to Option or vice versa. You can use methods like the ok method on Result or the ok_or method on Option to do the conversion explicitly.
## Generic Types, Traits, and Lifetimes
Generic are used to create abstracted function independent of types
Traits are used to create shared behavior among types
Lifetimes are used to do validate references
### Generics
### Traits
A trait defines the functionality a particular type has and can share with other types. Trait bounds to specify that a generic type can be any type that has certain behavior.


This restriction is part of a property called coherence, and more specifically the orphan rule, so named because the parent type is not present. This rule ensures that other people’s code can’t break your code and vice versa. Without the rule, two crates could implement the same trait for the same type, and Rust wouldn’t know which implementation to use.
### Lifetimes
## Writing Automated Tests
## An I/O Project
## Functional Language Features
## More about Cargo and Crates.io
## Smart Pointers
## Fearless Concurrency
## Object Oriented Programming Features of Rust
## Patterns and Matching
## Advanced Features
## Final Project
# Second Reading
