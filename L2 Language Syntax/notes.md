### Variables. Type is life: typing is important
- Safely typed languages like Go help us remain in control of our cost.
- You understand the problem better by understanding the data
- In order to understand cost we must understand size (of variables).
- integer type size depends on the architecture of the platform we are working on.
  - amd64: Since we are working on a 64 bit architecture, our pointer size or address size is going to be 64 bits.
    - Go looks at the address size for the arch we are on.
    - Then looks at the generic word size (word is a value that can change size depending on arch).
    - If address and word size is 64 bits/8 bytes, then the integer size will follow.
- The Go playground is a single-threaded, amd64p32 (addresses are 32 bits, words are also 32 bits, therefore int is too)
- We try to gain mechanical sympathies for the platform that we are building on when it comes to the address and word size.
- This adjustment is why we prefer to use integer type instead of precision based integer types except in very particular circumstances.

### Variables. Zero value declaration (var keyword)
- The cost of integrity is performance.
- Zero value is an integrity play in Go and it is very important.
- All memory that we allocate gets initialized at least to its zero value state.
- If I am going to declare a variable and I won't pre-initialize a specific value, I will use 'var' to declare it at its zero value.
- 'var' gives a zero value 100% of the time in Go. You don't get a zero value if you don't use 'var'.

### Variables. Short variable declaration (:= operator)
- This is a productivity-oriented operator.
- The compiler knows what data type corresponds to the value we are initializing.
- This operator comes a bit from Pascal
- Be consistent, do not initialize an integer value as 0 using the short variable declaration operator.

### Variables. Strings
- Strings are a "made-up" data type in most languages.
- Go has a unique way of dealing with strings.
  - The zero value of a string var is an empty string.
  - An empty string in Go is a 2-word data value: a pointer and an integer.
  - The pointer points to an array of bytes (or nil if not initialized with a value).
  - The integer holds the value for the length of this array of bytes.

### Variables. Conversion
- Go does not have casting, it has conversion. Integrity is number one priority.
- Conversion means that we may be taking a memory cost as we are converting values from one data type to other.
-  