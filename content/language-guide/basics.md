+++
title = "The Basics"
+++

Beef is a new programming language.

### Design goals
* High performance execution
 * No GC or ref counting overhead
 * Minimal runtime 
* Control over memory
 * Extensive support for custom allocators
 * Enchanced control over stack memory
* Low-friction interop with C and C++
 * Statically or dynamically link to normal C/C++ libraries
 * Support for C/C++ structure layouts and calling conventions
* Leverage LLVM infrastructure
 * Battle-hardened backend optimizer
 * ThinLTO link time optimization support 
* Enable fluid iterative development
 * Fast incremental compilation and linking
 * Runtime code compilation, including data layout changes
* Familiar syntax and programming paradigms
* Good Debugability
 * Emits standard debug information (PDB/DWARF)
 * Emphasis on good execution speed of debug builds
* Well-suite to IDE-based workflow
 * Compiler as a service
 * Fast and correct autocomplete results
 * Fast and trustworthy refactorability (ie: renaming symbols)

Optional interface conformance in extensions
Default interface methods
Expression blocks
'Self'
First-class functions (?)
Nested block comments
Sensible 'ref' rules- refs fall away unless re-asserted with 'ref' expression
	Readonly ref
Variable declarations in 'if'
Attributed member access ie: [Friend] [Inline]
Properties
	Including indexer property (can be multi-dimensional)
Allocationless method binding "=> Method" - passing to generic
Initializer syntax for arrays and structs - same for init as assign
Explicit inlining
Type inference
RAII
Protection specifiers
	Provide an "escape hatch" to pierce protection
Attributes
	Can even be used in member-reference contexts with things like [Friend] or callsite specifications like [Inline]

### Compilation Model

Workspace-wide compilation model
	Allows setting safety, tracing, and optimization options at
		Function, type, namespace, or project level
LLVM
ThinLTO
Og+
PDB
Mixed-optimization compilation
Methods/types can be selectively optimized
Release / Debug

### Compile Time Errors and Warnings
#unwarn

### Flow Control

Labeled scopes
	Allows stack allocation outside the current scope
	Allows Break/Continue out the current loop

### Reflection

### Interop

Painless FFI

### Extensions
Can even be added to types defined outside your own project

### Generics
Const generics
Generic methods

### Switches and Pattern Matching

Switches 
	Support for non-integral types
	Enforces comprehensive checks on enums
	Pattern matching

### Methods
Local methods
	Implicit capture

### Enums

Discriminated unions

### Memory Management

Custom allocators
	Mixin allocators can even allocate on the stack
Targeted stack allocations
Append allocations

### Defer

### Keywords

### Operators

.? Conditional
??
(.) casting
Cascade ..
Optional .?

Sensible operator overloading
	Spaceship operator for comparisons
	Operator requirements can be placed on interfaces

### Calling Conventions

Param Splatting
Method selection

### Ranges
Range-based for loops

### Method References

Lambdas
	Valueless method references
Method references - 
	Binding generic param to a non-allocating method reference instead of passing a delegate
Valueless method refs
Param forwarding
Functions / delegates / events

### Tuples

### Interfaces

Interfaces
	Concrete
	Const
	MethodRef
	'Self'

### Building

### Mixins

### Constants and Variables

Arrays
	Initialization - trailing comma
	Pointer result
Mixins
Events
Delegates
Variable shadowing
Immutable variables

### Data Types

Opaque types
Class / Struct
Boxing - including boxing to the stack
Primitive-typed structs
Unions
Uninitialized memory:
	Objects are zero-initialized by default
	Structs enforce that constructors explicitly initialized all values
	Structs on the stack must be fully initialized before being used
	Provides an "escape hatch" through the uninitialized "?" expression
Efficient layout
	Zero-sized types are supported
	Fields can be reordered to provide aligned access while reducing unused space
	A type's stride can be different than its size, removing unused filler at the end of a type that could be filled by actual data when extending the type or using it on the stack
"Const" is used for actual constants
Arrays
	With "type-erased" sizing and type-sized
Sized arrays (with optional bounds checking)
	Int-coercible char arrays (fast comparisons, using in switch statement)
Overloading

### Type Conversions

### Operators

### Error Handling

### Strings

Multi-line strings
UTF8
Native String type
	Interning

### Core Library

