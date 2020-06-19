# A Primer on (JavaScript) Programming

## Overview

A brief history of computing and programming, and a general introduction to JavaScript programming

## A. TL; DR

* **Key Point #1**: *The paradigm of transistor-based general-purpose computers, implemented with the von Neumann architecture and running programs written by human programmers in a (more-natural) general-purpose programming language, remains the predominant form of computer programming today.*
* **Key Point #2**: *JavaScript/ECMAScript has come to dominate the Web-application software development arena, and has become a full-fledged, robust general-purpose programming language in its own right since its humble origins as a simple scripting language, all the way through to the present day.*
* **Key Point #3**: *The role of the programmer is to translate user specifications (e.g., business requirements) into instructions that can be understood by the computer. This is generally done with the assistance of a high-level general-purpose programming language and corresponding development tools (e.g., Integrated Development Environments/IDEs).*
* **Key Point #4**: *The assignment operator* `=` *has relatively __low__ operator precedence, as the operand's expression(s) must first be evaluated in order to be assignable to a variable. Furthermore, the grouping operator* `()` *has the __highest__ priority, and is useful for either improving the semantics/readibility of the program, or deliberately increasing the precedence of a given expression (similarly to algebra).*

**!TO-DO ADD KEY POINTS**

## B. Contents

* C. A Brief History of Modern Computing and Programming
  * C-1. Early Era (1800s to 1940s)
    * The First Computers
    * The von Neumann Architecture
  * C-2. Middle Era (1940s to 1970s)
    * The Transistor
    * Assembly Languages
  * C-3. Modern Era (1970s to Present)
    * General-Purpose Programming Languages and Their Compilers
    * Computer Networking and Cross-Compatibility Issues
    * JavaScript and Web Applications
* D. The Perfect Language Doesn't Exist :(
* E. What Is a Program?
* F. JavaScript Programming: Fundamental Concepts
  * F-1. Values, Literals, and Data Types
  * F-2. Expressions and Statements
    * Variables and Identifiers
    * Operators and Expressions
    * Operator Precedence
    * ***Aside***: Logical Operators
    * Operator Precedence Examples
  * F-3. Control Structures
    * Conditionals
    * Loops
    * Function Calls
  * F-4. Values vs. References
  * F-5. Objects and Methods
    * Objects Overview
    * The Array Object
    * ***Aside***: Wrapper Objects
    * Objects in the Global Scope
    * ***Aside***: Instance Objects vs. Static Objects
    * The `console` Object
    * The Document Object Model (DOM)
* G. JavaScript Programming: A Guided Example
* H. Program Errors
* I. Key Takeaways
* J. References

## C. A Brief History of Modern Computing and Programming

### C-1. Early Era (1800s to 1940s)

#### The First Computers

Computation has a long, rich history, but its modern form originated approximately in the mid-1800s, with Charles Babbage’s conception of the **Analytic Engine**, a mechanical device which (in principle) would behave similarly to what would now be recognized as a general-purpose computer.

Through the turn of the 20th century, several other important developments had been independently discovered, including the formalization of key mathematical logic constructs by George Boole (a body of work now known eponymously as Boolean algebra). This continued progression of events up through the 1920s and 1930s culminated in the work of Alan Turing and his contemporaries. Turing’s seminal paper “*On Computable Numbers, with An Application to the Entscheidungsproblem*” (1936) formalized the modern notion of “**computation**”; a corollary of this monumental paper was the ability to precisely specify what is now known as a **general-purpose computer**.

Building on Turing’s work, and as part of the War effort, the first predecessors of the modern-day computer were conceived and built in the 1940s. The **ENIAC** is generally regarded as the first stored-program, general-purpose computer to have been built using electronic components (outcompeting its electro-mechanical, electro-magnetic, and other contemporaries); the ENIAC was effectively the first physical manifestation of Babbage’s Analytic Engine, conceived almost a whole century prior to that point.

These early machines were multi-ton in weight—occupying entire rooms—and had very limited memory and comparatively slow computational speed by modern standards. Furthermore, the binary (i.e., 1/0, or on/off) “language” understood by these machines was programmed using bulky components such as mechanical relays and vacuum tubes, which had performance issues and were susceptible to malfunction.

#### The von Neumann Architecture

These implementation difficulties notwithstanding, another important emergent property of these early computers was their fundamental design: the **von Neumann architecture**. This design (conceived by the mathematical prodigy John von Neumann and his colleagues) formed the basis of all modern computational devices—including the computers, smartphones, etc. in widespread use today.

The von Neumann architecture has the following general structure:

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/01-C1-vNA.JPG" alt="von Neumann Architecture")
 </p>

The structure is comprised of three key components:
* ***Memory*** - the storage area of the computer, which stores data and instructions of the computer program
* ***Central Processing Unit (CPU), or Processor*** - the “brain” of the computer, which performs computations and reads/writes data and program instructions to/from memory
* ***Inputs/Outputs*** - provides a user the ability to interact with the computer
  * ***Inputs*** include keyboard, mouse, audio/video peripherals (e.g., microphones and video cameras), network connectors (inbound), touch devices, etc.
  * ***Outputs*** include monitors, printers, audio/video peripherals (e.g., speakers), network connectors (outbound), etc.

### C-2. Middle Era (1940s to 1970s)

#### The Transistor

With the groundwork set by these early machines, several problems arose.

There was an obvious impracticality of such large, unwieldy devices which precluded any large-scale manufacture and adoption. A final critical piece was introduced to these nascent “proto-computers” with the invention of the **transistor** in the 1950s. The transistor is an electronic device which can behave as an “on/off” switch, and is a solid-state device having no moving/mechanical parts, thereby lending well to its stable, reliable operation. As the manufacturing process of transistors improved over time, the transistor was subsequently incorporated into computational devices to represent the fundamental **binary digit** (or **bit**), which underlies all computer hardware. The bit constitutes the simplest possible representation of data in computation: either on, or off. From this fundamental operation, larger, more complex structures such as digital logic gates (based on Boolean algebra) could be built, which ultimately hierarchically form into the full general-purpose computer.

Further innovation in integrated-circuit manufacturing technology over the subsequent decades propelled the transistor into a role of great prominence, as well as sparking the “second westward gold rush” of what eventually would become known today as *Silicon Valley*. The transistor was critically important in increasing the density of computational power and memory into increasingly smaller physical space (ultimately allowing for the mass production of consumer electronic devices), and it is widely regarded as one of—if not ***the***—most important inventions of the 20th century accordingly.

#### Assembly Languages

There was still, however, another problem: the process of “programming” these early computational devices required great skill and was highly tedious and error-prone, inasmuch as these machines were directly programmed in the “native” binary language understood by the machines. These early program were typically printed on punch cards or on tape read by the machine, which required intense labor and skill to write even trivial programs.

An [example](http://www.cs.uni.edu/~fienup/cs1410f11/lectures/Supplement_MARE_AL.pdf) "simple" binary program is as follows:
```
1010000000000000
0010000000010000
0001000000010010
0011000000010000
0010000000010001
1101000000010001
1000010000000000
1001000000001001
1001000000001110
0110000000000000
0001000000010000
0011000000001111
0010000000010000
1001000000000010
0111000000000000
0000000000000001
0000000000000000
0000000000000000
0000000000010011
0000000001001000
0000000001000101
0000000001001100
0000000001001100
0000000001001111
0000000000001101
0000000001010111
0000000001001111
0000000001010010
0000000001001100
0000000001000100
0000000000000000
```

A key innovation to address this issue was the development of **assembly languages**, starting in the late 1940s and into the subsequent decades. Assembly languages use mnemonic terms to represent the binary machine instructions and memory addresses of the computer, alleviating the need to explicitly program the computer in its native binary format.

The above binary program example can be represented in [MARIE](http://computerscience.jbpub.com/ecoa/4e/Login.aspx?ref=/ecoa/4e/default.aspx) (a fictitious/academic assembly language for a hypothetical computer architecture, used for pedagogical purposes) as follows:
```
		CLEAR
		STORE INDEX
WHILE,		LOAD STR_BASE
		ADD INDEX
		STORE ADDR
		LOADI ADDR
		SKIPCOND 400
		JUMP DO
		JUMP END_WHILE
DO,		OUTPUT
		LOAD INDEX
		ADD ONE
		STORE INDEX
		JUMP WHILE
END_WHILE,	HALT
ONE,		DEC 1
INDEX,		DEC 0
ADDR,		HEX 0
STR_BASE,	HEX 13
STR,		DEC 72	/H
		DEC 69	/E
		DEC 76	/L
		DEC 76	/L
		DEC 79	/O
		DEC 13	/carriage return
		DEC 87	/W
		DEC 79	/O
		DEC 82	/R
		DEC 76	/L
		DEC 68	/D
NULL,		DEC 0	/NULL CHAR

```

### C-3. Modern Era (1970s to Present)

#### General-Purpose Programming Languages and Their Compilers

While a vast improvement over explicit binary programming, assembly languages did not address several issues which were inherent in writing programs at the time, two of which are of particular note.
* Firstly, assembly languages lack **portability**. A given program written in a given machine’s **instruction set** (the binary instructions understood by that particular machine) were not directly portable/transferable to another machine—the program would have to be entirely rewritten all over in the new machine’s instruction set in order to execute the same program on the latter machine.
* Secondly, writing programs in assembly languages still subjected the programmer to solve problems within the constraints of the machine’s own instructions, rather than solving problems within the constraints of the problem domain itself and in a more natural, human-comprehensible manner.

Both of these issues (among others) were ultimately solved with the development of high-level, general-purpose programming languages and their associated compilers in the late 1950s through the 1970s (and to the present day).

A **general-purpose programming language** allows the programmer to specify instructions in a manner that is more reminiscent of natural language (e.g., English), using descriptive terms to perform **operations** (e.g., arithmetic, repetitive loops, etc.) and to denote **data** (e.g., variable declarations), rather than specifying binary machine instructions and binary memory addresses.

The previous example program can now be (truly) simply written in the general-purpose programming language JavaScript (discussed later) as follows:
```js
console.log("HELLO\rWORLD");
```

However, because the computer only understands binary instructions, the **compiler** (itself a specialized program) serves the role of “translator” from the human’s programming language to the computer’s native binary instructions. Compiler implementations are very complicated and even today are still an active area of research in the computer science arena, however, with decades of innovation preceding them, modern compilers can generate machine code from the **source code** (the program written in the general-purpose programming language) that is approximately just as efficient as that created by a skilled human assembly programmer.

> **Key Point #1**: *The paradigm of transistor-based general-purpose computers, implemented with the von Neumann architecture and running programs written by human programmers in a (more-natural) general-purpose programming language, remains the predominant form of computer programming today.*

#### Computer Networking and Cross-Compatibility Issues

Another key innovation was the development of computer **networking** (i.e., connecting computers into larger, integrated systems), ultimately resulting in the formation of the **Internet** in the 1980s and the **World Wide Web** in the early 1990s. (The profound impact of these technologies is readily self-apparent.)

The 1990s and 2000s marked a rapid transformation of globalized society and technology, including the proliferation of many wide-ranging computational devices and consumer appliances. Accordingly, one of the emerging challenges during this time was cross-compatibility of programs and software across these devices (a challenge that still remains today!).

In the mid-1990s, the general-purpose programming language **Java** was developed by Sun Microsystems to address this issue of **cross-compatibility**. One of Java’s core tenets was the notion of “*write once, run anywhere*.” To accomplish this, Java was implemented using a runtime environment (the **Java Runtime Environment**, including the **Java Virtual Machine**), which sits on top of each corresponding device’s operating system as a “*virtual computer*” that provides the ability to translate compiled Java source code (called Java **bytecode** in its compiled form) into the machine instructions specific to that particular target computer system. (Bytecode is essentially the “assembly program” run by the “virtual computer,” analogously to an assembly program running on the physical computer’s native binary instruction set.)

A simplified schematic of the Java programming language's implementation is as follows:

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/02-C3-Java.JPG" alt="The Java Runtime Ecosystem")
 </p>

Here, the source code written by the programmer in Java (`HelloWorld.java`) is first compiled to bytecode (`HelloWorld.class`) by the Java Runtime Environment (JRE), and then deployed to the corresponding target machine/operating system by the Java Virtual Machine (JVM), thereby constituting a cross-platform implementation system. 

Java’s popularity grew quickly during this time, and it has since become deeply rooted in the enterprise software development space. Microsoft released the programming language **C#** (analogously running on top of  the **.NET Framework** runtime environment) in 2000 as a direct competitor to Java, and many other runtime-environment-based programming languages have also emerged since then.

#### JavaScript and Web Applications

By the mid-to-late 1990s, as the Web became more prevalent and computers continued to become more powerful, the early form of modern **Web applications** began emerging. Up to this point, most programmed applications were developed to run in a native format (e.g., desktop applications) targeted to a specific operating system (e.g., Windows, Mac, Unix, etc.). However, with the interconnectivity provided by the Web, it was apparent that applications could similarly be useful in this growing cross-platform, cross-device landscape.

In 1995, Brendan Eich of Netscape developed the **JavaScript** programming language for use in its Netscape Navigator Web browser application, originally intended as a scripting language based on the Scheme programming language and implemented using an **interpreter** (analogous to a compiler, i.e., translator from the high-level programming language to machine code). Originally slated to be named “*LiveScript*” in its initial implementation and release, the Netscape team led by Eich elected to name the language “*JavaScript*” instead, capitalizing on the buzz surrounding its (otherwise unrelated) contemporary at the time, the aforementioned Java programming language.

The ensuing implementation challenges and “browser wars” subsequently to JavaScript’s initial launch and widespread adoption is beyond the scope of the present discussion, however, the key outcome of these events was the standardization of JavaScript’s programming language specification, under the oversight of the **European Computer Manufacturers Association** (**ECMA**), which correspondingly named its specification of the language as “**ECMAScript**” (partly due to trademark infringement concerns with respect to the name “JavaScript”). This is often abbreviated “**ES**” in reference to modern versions of the language (e.g., “**ES6**,” the 2015 release of the updated ECMAScript language specification, which marked a watershed moment in its maturity as a modern programming language).

Modern implementations (e.g., Google Chrome’s V8 and Mozilla Firefox’s SpiderMonkey engines) of the ECMAScript language specification (i.e., JavaScript) integrate its various features into a single “**JavaScript runtime environment**,” which provides the ability to program Web applications using the JavaScript programming language targeting the Web browser (e.g., Chrome, Firefox, etc.) as the medium of deployment of the fully functional, standalone Web application. This allows for great portability of Web applications, independently of the user’s operating system (the cross-platform issue is solved by vitue of the browser applications themselves, which are generally developed by the corresponding browser vendors for most major operating systems, e.g., Mac, Windows, and Linux).

A simplified schematic of the JavaScript runtime environment is as follows:

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/03-C3-JavaScriptRE.JPG" alt="The JavaScript Runtime Environment")
 </p>

(*N.B. [This informative article](https://medium.com/@olinations/the-javascript-runtime-environment-d58fa2e60dd0) provides a more comprehensive review of the various components of the open-source V8 JavaScript engine (Google Chrome’s implementation of the ECMAScript language and runtime environment), as well as the corresponding Web API (not formally part of the ECMAScript language specification) used for DOM manipulation of the Web browser page. V8 was also later adapted by Ryan Dahl to create **Node.js**, which provides a standalone JavaScript runtime environment allowing to deploy JavaScript applications outside/independently of the Web browser.*)

The proliferation of Web applications from the mid-2000s through the 2010s (and beyond) has largely displaced the use of native desktop applications, and consequently Web applications have become the predominant form of software applications used in practice today.

> **Key Point #2**: *JavaScript/ECMAScript has come to dominate the Web-application software development arena, and has become a full-fledged, robust general-purpose programming language in its own right since its humble origins as a simple scripting language, all the way through to the present day.*

[:arrow_up_small: Return to top](#overview)

## D. The Perfect Language Doesn't Exist :(

With all of the innovations that have occurred in the past century of computation and programming, there are still performance limits of modern computational devices, both in practical and in theoretical terms.

Referring back to the von Neumann architecture model, both processor speeds (i.e., machine operations per unit time) and memory capacity (i.e., total bits of stored information) are ***finite***. Modern computers have processor speeds measured in GHz (billions of operations per second) and memory capacities measured in Gigabytes/GB (billions of bytes of addressable memory, where a “**byte**” is a conventional grouping of bits into a set of eight). With rapid technological advancements, processor speeds and memory capacities have increased at an exponential rate in the decades spanning from the mid-20th century through the present day. However, while modern applications are far more robust than even as recently as a decade ago, with the explosive growth of devices and data, there are still many applications and problem domains that even the most advanced computers must contend with.

Furthermore, general-purpose programming languages ultimately become machine-code instructions, and therefore are subject to the constraints of the machine. For this reason, computers in their modern form do not possess “intelligence” and “insight” in the same (nondeterministic) way that a human does, and are incapable of interpreting ambiguous or unspecific requirements accordingly.

Therefore, an “*ideal*” computer would be one with infinite processor speed and infinite memory, with the ability to translate ambiguous natural-language specifications directly into a set of precise instructions. This would also obviate the need for computer programmers in the first place (fortunately for programmers, this is not a credible threat!). Interestingly, even if such an “ideal” (*read*: impossible) machine were available, there are still many mathematical and non-trivial computational problems that are beyond its capabilities!

With these considerations, when a general-purpose programming language is designed and implemented, there are inherent **trade-offs** that are made accordingly. These typically involve a compromise between high performance (which requires programming “closer to the machine”) vs. readability and expressiveness (which is more similar to natural language, but at the price of more “overhead” to generate the machine instructions from the programmer’s source code resulting in slower performance).

Below is a brief survey of a few representative modern, popular general-purpose programming languages in common use today.

| Programming Language | Creator | Current Specification Developer(s) | Language Specification | Implementation | Representative Application Domains | Comments |
| :---: | :---: | :---: | :---: | :---: | :--- | :--- |
| C | Dennis Ritchie (1970s) | ISO/IEC JTC 1 | ISO/IEC 9899 | compiled (e.g., gcc, Clang) | <ul><li>operating system kernels</li><li>embedded hardware systems</li><li>compilers</li></ul> | Used in high-performance applications, and has more explicit constructs reminiscent of assembly & machine code |
| C++ | Bjarne Stroustrup (1980s) | ISO/IEC JTC 1 | ISO/IEC 14882 | compiled (e.g., gcc, Clang, MS Visual C++) | <ul><li>high-performance applications (e.g., game engines, real-time audio/video signal processing, etc.)</li><li>embedded hardware systems</li></ul> | Originally developed as an "improvement" (++) to C with the addition of classes, it has since become widespread in hardware systems and influenced later languages such as Java |
| Java | James Gosling (1990s) | Oracle | The Java® Language Specification | compiled and interpreted via the Java Runtime Environment & Java Virtual Machine |  <ul><li>cross-platform desktop applications</li><li>Web applications</li></ul> | Popularized the runtime environment paradigm of application development and deployment, and is still in wide use today |
| C# | Anders Hejlsberg (2000s) | <ul><li>Microsoft</li><li>ISO/IEC JTC 1</li><li>Ecma International</li></ul> | ISO/IEC 23270, ECMA-334 | compiled and interpreted via the .NET Framework & Common Language Runtime (CLR) | <ul><li>cross-platform desktop applications</li><li>Web applications</li></ul> | Developed by Microsoft as a direct competitor to Java, these languages generally compete in similar markets (e.g., enterprise software development) |
| Python | Guido von Rossum (1990s) | The Python Software Foundation (PSF) | The Python Language Reference (based on Python Enhancement Proposals, or PEPs) | interpreted (standard CPython implementation) | <ul><li>Data science and analytics</li><li>Machine learning and artificial intelligence</li><li>Education (computer science & programming)</li><li>Web applications</li></ul> | Having gained popularity into the 2010s and beyond, Python is widely used in academia and in data application domains. Python is less performant than the other languages indicated above, a design trade-off made in favor of its expressiveness (i.e., more reminiscent of natural human language). |
| JavaScript | Brendan Eich (1990s) | Ecma International | ECMA-262 | interpreted by JavaScript runtime environment (e.g., Google Chrome V8, Mozilla FireFox SpiderMonkey, Node.js, etc.) | <ul><li>Web applications</li><li>Native applications (desktop & mobile)</li></ul> | JavaScript has come to dominate the Web application developed landscape through the 2010s (and beyond), often touted by its enthusiasts as the "most used programming language" due to the ubiquity of the modern Web |

[:arrow_up_small: Return to top](#overview)

## E. What Is a Program?

With the preceding discussion regarding the historical context of computation and programming now concluded, it is worthwhile to ask a fundamental question: what *is* a **program**, anyways? 

A program is simply a set of instructions, i.e., ultimately the machine instructions performed by the computer’s constituent transistor-implemented bits.

The famously titled textbook “Algorithms + Data Structures = Programs” (1976) by computer scientist Niklaus Wirth provides an insightful description of the fundamental essence of a “*program*.”
* An **algorithm** is a precisely specified sequence of instructions (e.g., a step-by-step recipe to prepare a dish).
* A **data structure** (e.g., an array) is a organized grouping of information, which is typically manipulated by algorithms to achieve a certain desired result or outcome.

A program, then, is simply a collection of data structures and algorithms, which vary in scale and complexity correspondingly to the underlying problem that the program is intended to solve.

Therefore, while the computer hardware is only “aware” of its constituent bits (transistors), it is the programmer-specified data structures stored in its memory and corresponding programmer-specified algorithms performed (computed) by its processor on those data structures which confer “meaning” on those bits—be it bank account information, moving pictures on a screen, text messages, spreadsheets, etc. Indeed, the information stored in and represented by the underlying physical circuitry of any given computational device is only “meaningful” to the human user of that device, by virtue of the programmer’s implementation of the user’s software applications per their (potentially ambiguous) specification.

> **Key Point #3**: *The role of the programmer is to translate user specifications (e.g., business requirements) into instructions that can be understood by the computer. This is generally done with the assistance of a high-level general-purpose programming language and corresponding development tools (e.g., Integrated Development Environments/IDEs).*

[:arrow_up_small: Return to top](#overview)

## F. JavaScript Programming: Fundamental Concepts

This section will review fundamental programming principles, using JavaScript as a representative case study of a modern general-purpose programming language.

The following is a "roadmap" of Section F, intended to provide a "mental model" for conceptualizing the hierarchical structure of the programming process.

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/00-01-F0-Roadmap.JPG" alt="Section F Roadmap")
 </p>

### F-1. Values, Literals, and Data Types

The atomic unit of any computer program is the **value**, which is represented as binary digits (bits) by the constituent hardware (i.e., transistors) of the computer system on which the program is ultimately run.

The most fundamental level of human semantics provided by the programming language to the computer is the notion of a **data type**. While the computer itself only understands bits (sequences of 1s and 0s), the problem domain and programmer have a more intuitive notion of useful “*values*.” Accordingly, JavaScript provides several **primitive data types** to represent these values. These primitive data types are as follows:

| Primitive Data Type | Representative Literal(s) | Description |
| :---: | :---: | :---: |
| Number | `5`, `3.14` , `NaN` | Represents numbers and used in arithmetic operations |
| String | `'Hello World'` | Represents text information |
| Boolean | `true`, `false` | Represents true/false values and used in control structures (discussed later) |
| Null | `null` | Semantically represents the *deliberate absence/omission* of a value |
| Undefined | `undefined` | Semantically represents an *unknown/indeterminate* value |

*(N.B. Symbol and BigInt are primitive data types also provided by JavaScript as of ES2020, however, these will not be considered further for purposes of discussion. See [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures) for further discussion of primitive values.)*

A common term when referring to a value from a primitive data type is a **literal**. As this terminology suggests, primitive values are “hard-coded” in the programming languages and are unchanging/**immutable** (e.g., the value 5 is understood to be a numeric integer—it would not make sense to “*change*” what 5 fundamentally represents in the programming language).

Additionally, JavaScript provides many additional *non*-primitive data types (e.g., objects, arrays, and functions). These provide a more robust feature set for the corresponding values (i.e., to represent more complicated values and data structures for a particular problem), however, this also comes at the expense of implementation and performance overhead. These non-primitive data types will be revisited again later in this section.

### F-2. Expressions and Statements

#### Variables, Identifiers, and Keywords

Values in isolation are not particularly useful in solving a problem with a computer program. In order to confer *utility* onto these values, they can be stored in **variables** and used in arbitrary **expressions**.

First, consider the simple **variable assignment** of primitive data types using the assignment operator `=`:
```js
let a = 5; // assign number literal 5 to variable a
a = ‘Hello World’; // re-assign variable a to a string literal ‘Hello World’
```
The above code demonstrates the most fundamental unit of a program: the **statement**. Shown above are two statements in succession, written on separate lines, with each statement terminated by a semicolon (`;`). All programs are simply a list of such statements listed in succession, with growing complexity concomitantly with the complexity of the problem the program is solving. As an analogy, if a program were a *book*, the statement would be a *sentence* (composed of *words*, i.e., values and expressions).

Variables provide the ability to “*label*” data in memory, thereby providing a rudimentary data structure. This allows the programmer to work with variable names rather than (binary) memory addresses, greatly increasing productivity of the programmer and the semantics of the program; the JavaScript interpreter will handle the rest (i.e., connecting the label to the binary memory address)!

**!TO-DO: Add identifiers & keywords content**

#### Operators and Expressions

Additionally, values and variables can be combined and manipulated into **expressions** with the help of **operators** provided by the JavaScript programming language (these operators ultimately map to the machine instructions performed by the processor on the target machine; this, again, is handled “under the hood” by the JavaScript interpreter).

Some representative expressions are as follows:
```js
// this is a simple arithmetic expression via the arithmetic + operator
5 + 5;

// this is a simple concatenation operation via the concatenation + operator, 
// with the resulting expression (a string, ‘Hello world’) assigned to the variable str
const str = ‘Hello ‘ + ‘world’; 

// the && (AND) operator evaluates its operands (true and true) and returns a Boolean value (true), 
//which is assigned to the variable isTrue
let isTrue = true && true;
```
(*N.B. While not in scope of the present discussion, it is important to be mindful of **type coercion** when combining operands of different data types into expressions using operators. See [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness) for further reference.*)

#### Operator Precedence

When working with operators to create arbitrarily complex expressions in JavaScript, it is important to note the **operator precedence** of a given operator, where an operator can take one, two, or three operands (values and/or expressions), correspondingly referred to as unary, binary, and ternary (respectively) operators.

An abbreviated table of select operators and their precedence is as follows (see [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) for full reference):

| Precedence Rank | Operator Type | Associativity | Operand(s) | Notation | Example |
| :---: | :---: | :---: | :---: | :---: | :---: |
| 21 (*highest*) | Grouping | N/A | N/A | `(...)` | `(1 + 2);` |
| 20 | <ul><li>Member Access</li><li>Index Access</li><li>Function Call</li></ul> | L → R | 2 | <ul><li><code>op1.op2</code></li><li><code>op1[op2]</code></li><li><code>op1(op2)</code></li></ul> | <ul><li><code>obj.key;</code></li><li><code>arr[index];</code></li><li><code>f('hello');</code></li></ul> |
| 18 | <ul><li>Postfix Increment</li><li>Postfix Decrement</li></ul> | L ← R | 1 | <ul><li><code>op1++;</code></li><li><code>op1--;</code></li></ul> | <ul><li><code>i++;</code></li><li><code>j--;</code></li></ul> |
| 17 | <ul><li>Logical NOT</li><li>Unary Plus</li><li>Unary Negation</li><li><code>delete</code></li></ul> | L ← R | 1 | <ul><li><code>!op1</code></li><li><code>+op1</code></li><li><code>-op1</code></li><li><code>delete op1</code></li></ul> | <ul><li><code>!true;</code></li><li><code>+5;</code></li><li><code>-3;</code></li><li><code>delete obj.key;</code></li></ul> |
| 16 | Exponentiation | L ← R | 2 | `op1 ** op2` | `3 ** 4;` |
| 15 | <ul><li>Multiplication</li><li>Division</li><li>Remainder (Modulo)</li></ul> | L → R | 2 | <ul><li><code>op1 * op2</code></li><li><code>op1 / op2</code></li><li><code>op1 % op2</code></li></ul> |<ul><li><code>2.5 * 3;</code></li><li><code>10 / 7;</code></li><li><code>num % 2;</code></li></ul> |
| 14 | <ul><li>Addition, Concatenation</li><li>Subtraction</li></ul> | L → R | 2 | <ul><li><code>op1 + op2</code></li><li><code>op1 - op2</code></li></ul> |<ul><li><code>5 + 7;</code></li><li><code>12 - 8;</code></li></ul> |
| 12 | <ul><li>Less Than</li><li>Less Than or Equal</li><li>Greater Than</li><li>Greater Than or Equal</li><li><code>in</code></li></ul> |  L → R | 2 | <ul><li><code>op1 < op2</code></li><li><code>op1 <= op2</code></li><li><code>op1 > op2</code></li><li><code>op1 >= op2</code></li><li><code>op1 in op2</code></li></ul> | <ul><li><code>5 < 6;</code></li><li><code>5 <= 5;</code></li><li><code>3 > 2;</code></li><li><code>3 >= 3;</code></li><li><code>for (let key in obj);</code></li></ul> 
| 11 | <ul><li>Equality</li><li>Inequality</li><li>Strict Equality</li><li>Strict Inequality</li></ul> | L → R | 2 | <ul><li><code>op1 == op2</code></li><li><code>op1 != op2</code></li><li><code>op1 === op2</code></li><li><code>op1 !== op2</code></li></ul> | <ul><li><code>3 == '3';</code></li><li><code>2 != '3';</code></li><li><code>3 === 3;</code></li><li><code>2 !== 3;</code></li></ul> |
| 6 | Logical AND | L → R | 2 | `op1 && op2` | `true && true;` |
| 5 | Logical OR | L → R | 2 | `op1 \|\| op2` | `true \|\| false;` | 
| 4 | The Conditional (Ternary) Operator | L ← R2 ← R1 | 3 | `op1 ? op2 : op3` | `1 === 1 ? 'true' : 'false';` | 
| 3 | Assignment | L ← R | 2 | <ul><li><code>op1 = op2</code></li><li><code>op1 **= op2</code></li><li><code>op1 *= op2</code></li><li><code>op1 /= op2</code></li><li><code>op1 %= op2</code></li><li><code>op1 += op2</code></li><li><code>op1 -= op2</code></li></ul> | <ul><li><code>a = 3;</code></li><li><code>a **= 3;</code></li><li><code>a *= 3;</code></li><li><code>a /= 3;</code></li><li><code>a %= 3;</code></li><li><code>a += 3;</code></li><li><code>a -= 3;</code></li></ul> |
| 1 (*lowest*) | Comma/Sequence | L → R | 2 | `op1 , op2` | `[1 , 2];` |

*(N.B. The conditional operator* `?:` *is also called the **ternary** operator because it is "the" one operator which receives **three** operands.)* 

The operator rules are listed for each operator with respect to its number of **operands** (where the operands `op1`, `op2`, and `op3` in general can be either values or arbitrary expressions) and **associativity** (i.e., left-to-right L → R, or right-to-left L ← R).

#### ***Aside***: Logical Operators

For reference, the logical operators `!` (NOT), `&&` (AND), and `||` (OR), which are used commonly in conditional statements, exhibit the following behavior (commonly called their respective **truth tables**):

| `op1` | `op2` | `!op1` | `op1 && op2` | `op1 \|\| op2` |
| :---: | :---: | :---: | :---: | :---: |
| `true` | `true` | `false` | `true` | `true` |
| `true` | `false` | `false` | `false` | `true` |
| `false` | `true` | `true` | `false` | `true` |
| `false` | `false` | `true` | `false` | `false` |

*(N.B. These Boolean operators use an evaluation scheme called **short-circuiting** or **lazy evaluation**. In* `op1 && op2` *, if* `op1` *is* `false` *, this renders the entire expression* `false` *by default and therefore* `op2` *is not evaluated at all. Similarly, in* `op1 || op2` *, if* `op1` *is* `true` *, this renders the entire expression* `true` *by default and therefore* `op2` *is not evaluated at all.)*

#### Operator Precedence Examples

In general, the JavaScript interpreter reads the JavaScript source code file (e.g., `index.js`) from top-to-bottom, and then evaluates each statement encountered from left to right (or right-to-left for the corresponding operators with L ← R associativity). Once an operator is encountered, the corresponding operand(s) is/are evaluated and then the operation is performed, returning a resulting value. Operators can be generally chained in this manner (i.e., where the resulting value is passed as an operand to a subsequent operator), giving rise to arbitrarily complex expressions and statements.

A few illustrative examples demonstrating operator precedence are as follows:

```js
/* 
1) Arithmetic expressions behave similarly to traditional algebra
*/

let a = 3 + 2 / 4;
// Operators (Rank): "=" (3), "+" (14), "/" (15)
// 2 / 4 is evaluated first, giving 0.5
// 3 + 0.5 is evaluated, giving 3.5
// 3.5 is assigned to a

a = (3 + 2) / 4;
// Operators: "(...)" (1), "+" (14), "/" (15)
// (...) increases the precedence of the expression 3 + 2, which is evaluated first to give 5
// 5 / 4 is evaluated, giving 1.25
// 1.25 is assigned to a

a = 3 ** 2 ** 2;
// Operators: "=" (3), "**" (16)
// ** has a right-to-left associativity, and since both are at the same precedence, the right expression
// is evaluated first...
// 2 ** 2 is evaluated, giving 4
// 3 ** 4 is evaluated, giving 81
// 81 is assigned to a

/*
2) Boolean expressions are often used in if-else statements to form complex expressions
    (if-else statements are discussed later)
*/

if(!false || true && true && !false || false) {
    // statement(s) to evaluate if condition evaluates to "true"
}
// In order to evaluate the conditional expression provided to the if clause, it must be
// evaluated (i.e., simplified to a Boolean)
// Operators: ! (17), || (5), && (6)
// ! has the highest precedence, so the Boolean expression first simplifies as follows...
// true || true && true && !false || false
// true || true && true && true || false
// && has the next-highest precedence, so the expression further simplifies as follows...
// true || true && true || false
// true || true || false
// || has the lowest precedence, so the expression is finally simplified as follows...
// true || false
// true

(!false
    || (true && true && !false) 
    || false
 );
// The conditional expression show above is equivalent to the previous one, but is made more readable 
// with parenthesization and indentation

/*
3) Access of array indices and object members can also involve complex expressions
    (arrays and objects are discussed later)
*/

const obj = {
    key1: [[1, 2], 3, 4],
    key2: {
            key: 'value'
	  }
}

obj.key1[0][1];
// Operators: "." (20), "[...]" (20)
// . and [] are at the same precedence, so this "chained" expression is evaluated in order from left to right...
// obj.key1 accesses the key "key1" of obj, having value [[1, 2], 3, 4] (an array)
// obj.key1[0] accesses element 0 of obj.key1, having value [1, 2] (an array)
// obj.key1[0][1] accesses element 1 of obj.key1[0][1], giving the final value 2

obj.key2.key;
// Operators: "." (20)
// As before . are at the same precedence, giving another "chained" expression evaluated left to right...
// obj.key2 accesses the key "key2" of obj, having value { key: 'value' } (an object)
// obj.key2.key accesses the value stored in obj.key2.key, giving the final value 'value'

let arr = [4, 5, 6, 7];

arr[arr.length - 1];
// Operators: "[...]" (20), "." (20), "-" (14)
// This statement has the form op1[op2];. Since op2 is an expression, it must first be evaluated/simplified
// in order to determine the index to access...
// arr.length evaluates to 4
// 4 - 1 evaluates to 3
// Therefore, arr[3] gives the final value 7
```

> **Key Point #4**: *The assignment operator* `=` *has relatively __low__ operator precedence, as the operand's expression(s) must first be evaluated in order to be assignable to a variable. Furthermore, the grouping operator* `()` *has the __highest__ priority, and is useful for either improving the semantics/readibility of the program, or deliberately increasing the precedence of a given expression (similarly to algebra).*

In practice, most operator precedence rules are intuitive, however, when dealing with complicated expressions, the precedence table can be referenced to disambiguate the order of operations (N.B. this may also be indicative of a candidate expression requiring further refactoring/simplification prior to use). **White space** and **parenthesization** additionally can assist with visually promoting greater readability of a complex expression (e.g., in if-else condition clauses, discussed later in this section).

### F-3. Control Structures

Up to this point, relatively simple “programs” have been discussed (indeed, a single statement in a source-code file constitutes a valid/”complete” program—albeit a rather trivial one).

In general, a typical program is written as a series of statements in succession, following the logical and thematic organization of the particular problem that it is targeting (e.g., user specifications). Conceptually, this can be modeled diagrammatically as follows:

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/04-F3-ProgramSequence.JPG" alt="A Model of a Program's Sequence")
 </p>

While it is possible to write fairly complicated programs in this manner, as programs grow in size and complexity, such a “wall” of instructions can quickly become unwieldy from an organizational standpoint.

To assist with this, virtually all modern programming languages (including JavaScript) provide several **control structures** to provide enhanced behavior of the program’s flow from its start to the end of its terminal statement prior to halting execution.

The principal control structures that will be discussed in the following subsections are as follows:

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/05-F3-ControlStructures.JPG" alt="A Model of a Program's Sequence")
 </p>

#### Conditionals

Conditional statements allow the program to direct/route the instruction sequence on specific conditions; an analogy for this would be a “selector switch” to route the path of electrical or water flow.

The main constructs provided for this purpose in JavaScript are the `if`/`else` construct (and related ternary operator, `? :`), as well as the `switch`/`case` construct. (N.B. For brevity, only `if`/`else` will be considered here for purposes of discussion.)

The simplest possible conditional construct is a standalone `if` statement. The `if` keyword evaluates an expression (which can be arbitrarily complex) to determine whether it is “truthy” or “falsy.” If “truthy,” then the subsequent statement(s) is/are evaluated, otherwise no action is performed.

In JavaScript, the following values are evaluated as “falsy” (via [MDN](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)):

`false`, `0`, `-0`, `""` (empty string), `null`, `undefined`, `NaN`

In general, any value that is non-"falsy" is therefore "truthy". Conditional clauses (i.e., in an `if` statement) are typically (arbitrarily complex) *expressions* that evaluate to a Boolean value, however, a single value can also be simply passed and evaluated for its "truthiness" or "falsiness" in this manner.

The following are examples of standalone `if` statements:
```js
const isTrue = true;

// Condition evaluates to true, and the statement is consequently evaluated
if (isTrue) {
    console.log(“The if condition has been met, this statement is evaluated :)”);
}

// Condition evaluates to false, and the statement is consequently NOT evaluated
if (!isTrue) {
    console.log(“The if condition has not been met, this statement is not evaluated :(“);
}
```

Additionally, an `else` clause can be paired with a preceding `if` statement to provide routing/selection between the target statements. For example:
```js
const isTrue = true;

if (!isTrue) {
    console.log(“The if condition has not been met, this statement is not evaluated :(”);
} else {
    console.log(“Since the if condition has not been met, this statement is evaluated instead :)“);
}
```

These `if`/`else` statements can be further paired/chained to form arbitrarily complex routing of statements. It is a common idiom to write `if` / `else if` / … / `else` blocks for this purpose, as follows:
```js
const condition = 2;

// Construct A
if (condition <= 1) {
    // condition1
} else if (condition > 1 && condition < 3) {
    // condition2
} else {
    // condition3a
}
```

However, be advised that by default each `else` pairs to its most recently preceding `if` when written in this manner. Hence, note the distinction between the preceding example and the following:
```js
const condition = 2;

// Construct B
if(condition !== 2) {
    if (condition <= 1) {
        // condition 1
    } else {
        // condition 3b
    }
} else if (condition > 1 && condition < 3) {
    // condition2
}
```
Diagrammatically, the distinction between these two sets of constructs is as follows:

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/06-F3-ifelse.JPG" alt="Constructs A and B")
 </p>

Thus, it is important to be mindful of `if`/`else` pairings and to use brackets `{ … }` and appropriate **indentation** (where applicable) to explicitly denote the intended behavior in such “nested” constructs.

#### Loops

Looping/repetition provides the ability to execute a statement multiple times, either for a specified number of **iterations** (e.g., `for` loop) or until a terminal condition is met (e.g., `while` and `do … while` loops). (N.B. This section will restrict focus to the `for` loop construct for the sake of brevity.)

A common use case of the `for` loop is to perform actions on an array, whose iterations correspond to the array’s constituent elements, and within the bounds of its `length` property. (Arrays are discussed in further detail later in this section.)

The `for` loop has the following structure:
`for(`*start index*` ; `*termination condition*` ; `*increment of iterated variable*`) { … }`

The following is an example of a `for` loop construct:
```js
let sum = 0;
const arr = [1, 2, 3, 4]; // an array with arr.length === 4

for(let i = 0; i < arr.length; i++) {
    sum += arr[i];
}

console.log(sum); // 10
```

This loop construct represents the following:

| `i` | `i < arr.length` | `arr[i]` | value of `sum` after current iteration |
| :---: | :---: | :---: | :---: |
| 0 | `true` | 1 | 1 |
| 1 | `true` | 2 | 3 |
| 2 | `true` | 3 | 6 |
| 3 | `true` | 4 | 10 |
| 4 | `false`| *(loop terminated)* | *(loop terminated)* |

*(N.B. `i`, `j`, and `k` are conventionally used as variable names for iterated indices (e.g., in loops).)*

While out of scope for the present discussion, be advised that the `break`, `continue`, and `return` statements can be used to add further complex routing inside of loop constructs. (See [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration) for more information.)

#### Function Calls

A **function** allows to *modularize* a program into specific units/tasks, which helps with organizing the program’s code, particularly when a given task is performed repeatedly, or if a group of statements form a semantically distinct operation.

In general, a function is first **defined**, as in the following example:
```js
function simpleTask() {
    console.log(‘This is a simple function!’);
}
```

Once a function is declared, it can then be **invoked** (or **called**) as follows:
```js
simpleTask();
```

Analogously to a mathematical function, the role of a function is to route inputs and outputs. In JavaScript, these are represented by **parameters** and the `return` statement, respectively. However, note that neither parameters nor a `return` statement are required for a function definition to be valid, which in general can have the following forms (using **arrow-function notation** for brevity):

| input↓ \\ output→ | No `return` | Has `return` |
| :---: | :---: | :---: |
| **No parameters** | `() => { ...statements... }` | `() => { ...statements... return ...; }` |
| **Has parameters** | `(params) => { ...statements... }` | `(params) => { ...statements... return ...; }`  |


*(N.B. In the function declaration, the inputs are called **parameters**. In the corresponding function invocation/call, the corresponding **arguments** are supplied to the function, which become the parameters used in the function body’s statements.)*

As an example of a function definition having a parameter and a `return` value, and its subsequent function call, is as follows:
```js
const name = ‘Matt’;

function greet(name) { // here, “name” is the parameter, used inside the function body
    return `Hello, ${name}`;
}

console.log(greet(name)); // here, “name” (having value ‘Matt’) is passed as an argument to function greet()
```

It is common to wonder when/why functions are used. To reiterate the previous point, the purpose of a function is to *modularize the code*. In fact, many operations are so common or otherwise useful that most modern languages (including JavaScript) provide a **standard library** of functions for common tasks. These can be regarded as an exemplar for function design, as they are the product of the collective decades of programming experience by the designers of programming languages and their predecessors. Some of these standard features provided in JavaScript will be discussed later in this section. (See [MDN JavaScript reference]( https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference) for a full catalog of built-in features in JavaScript.)

Ultimately, as with the other control structures, functions provide another tool to the programmer for organizing their code and for modeling real-world, non-trivial problems. The selection (or omission) of input parameter(s) and of a `return` value depends on the intended purpose of the function itself. 

### F-4. Values vs. References

*N.B. The diagrams in this section were generated using the [Python tutor JavaScript ES6 visualizer tool](http://www.pythontutor.com/visualize.html#mode=edit), a very useful pedagogical device for visualizing the step-wise operation of the JavaScript source code.*

Having discussed programs, statements, and control structures, discussion can now proceed to more complex subject matter, pertinent to the design of “real-world” applications.

Recall from the beginning of this section that **values** can be generally categorized as primitive vs. non-primitive. As was indicated previously, primitive values are “hard-coded” values in memory and are **immutable** (i.e., unchanging). Consider the following variable declarations of the respective primitive data types:
```js
let num = 5;
let str = 'Hello World';
let isBoolean = true;
let nullVal = null;
let undefVal;
```

This can be represented diagrammatically in the computer memory as follows:
<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/07-F4-Primitives.JPG" alt="Primitives in memory")
 </p>
	
Conversely, non-primitives are not “hard-coded” in memory in this same manner. The primary non-primitives that will be considered are the **array** and **object**. In the case of arrays and objects, the “value” held by these “data types” is not a “hard-coded value” (as in the case of primitives), but rather a **reference** to a memory location holding the contents of the array or object.

*(N.B. In JavaScript, virtually all non-primitives are modeled as **objects** via **prototypal inheritance** from the global object* `Object`*. This matter is beyond the scope of present discussion, however, the interested reader is referred to [MDN]( https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) for elaboration on this topic.)*

Consider the following examples of an array (`arr`) and an object (`obj`):
```js
const arr = [1, 2, 3, 4];

const obj = {
    key1: ‘value 1’,
    key2: ‘value 2’
}
```

In memory, these are represented as follows:
<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/08-F4-NonPrimitives.JPG" alt="Non-primitives in memory")
 </p>
	
As per the diagram, the “values” held by the variables `arr` and `obj` are **references** to another location in memory where the corresponding data structure is constructed (this is known as **dynamic memory allocation**; see [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management) for more information regarding memory management by the JavaScript runtime). 

Now, consider the following slight modification to the code as follows:
```js
const arr = [1, 2, 3, 4];

const obj = {
    key1: ‘value 1’,
    key2: arr // change value from 'value 2' to arr
}
```

The modified diagram is now as follows:
<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/09-F4-arrRef.JPG" alt="arr reference")
 </p>
	
Because `arr`’s reference is now also “labeled” by `obj.key2`, they both refer to the same memory location.

Now, note the result of the following statements and the corresponding diagram:
```js
obj.key2[0] = ‘Side effect!’;
console.log(arr[0]); // ‘Side effect!’
```
<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/10-F4-SideEffects.JPG" alt="Side effect")
 </p>
	
Observe that modification of `obj.key2[0]`’s value also made the corresponding change to `arr[0]`, due to mutual reference to the same memory location where the values of `arr`'s elements are stored. Thus, arrays (and objects) are **mutable**, i.e., can be changed during program execution. This scheme of “passing by reference” when using non-primitives (e.g., arrays and objects) gives rise to a phenomenon known as **side effects**, whereby a referenced value may cause (potentially unwanted) changes in program which may be difficult to detect in the code.

One may therefore ask: so, why even bother with this *referencing* scheme, rather than simply hard-coding the *values* of non-primitives (e.g., `arr` and `obj`)? This is mainly an implementation optimization: hard-coding the values requires passing *copies of the entire value* (e.g., in function calls, variable assignments, etc.), which can become unwieldy and memory-intensive for arbitrarily complex arrays and objects. This is not an issue with primitives, however, which are implemented by the interpreter in a “light-weight” and efficient/optimized manner, and are therefore “passed by (hard-coded) value” accordingly without issues.

Ultimately, objects and arrays allow to build much more complex data types and data structures from primitives (and other non-primitives, e.g., arrays of objects, objects of objects, objects containing arrays, etc.) in order to represent real-world problems that are meaningful to the programmer and to the problem domain (but ultimately only understood by the machine as 1s and 0s), and hence why they are a staple feature of JavaScript and in other programming languages.

### F-5. Objects and Methods

#### Objects Overview

As a final topic of discussion, the concept of objects will be further considered.

In general, **objects** are comprised of two “components”:
* **properties** - attributes of the object 
* **methods** - functions performed by and/or on the object

These “components” are often referred to as **members** of the object. A common notation/formalism involving objects (i.e., accessing an object's members) is `object.property` and `object.method(…)`.

*(N.B. This formalism was popularized in the 1980s with the wide-spread proliferation of the **object-oriented programming** paradigm, which remains the predominant programming paradigm for modern software development today.)*

Objects provide the ability to build complex, robust data types to model real-world problems. It allows to “package” an object into a semantic unit of properties (attributes) and methods (functions) particular to the instantiated objects (i.e., variables) of that particular object type.

#### The Array Object

As a first “case study” of this object paradigm, recall the aforementioned **array** data type (itself a specialized object). An abbreviated diagram of a generic array `arr` is as follows (see [MDN]( https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) for the full reference set of properties and methods of array objects):

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/11-F5-arrUML.JPG" alt="pseudo-UML diagram for Array object")
 </p>

*(N.B. Methods are used like functions and have similar behavior, i.e., they can receive input **parameters**, which correspond to the arguments passed via an analogous **method call*** `arr.method(arg(s));` *, and can also return a value. A method is essentially a "specialized function" that belongs to the object, e.g.,* `arr` *.)*

The property `length` is accessed as `arr.length` and returns the number of elements contained in the array `arr`. The **methods** of `arr` are further described as follows:

| Array Method | Description | Parameter(s) | Return Value | MDN Reference |
| :---: | :---: | :---: | :---: | :---: |
| `.push()` | Add element(s) to end of `arr` | `element1`*[*`, element2, ..., elementN`*]* | Updated `arr.length` value | [Array.prototype.push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push) |
| `.pop()` | Remove last element from `arr` | (no parameters) | The element removed from `arr`, or `undefined` if `arr.length === 0` | [Array.prototype.pop()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop) |
| `.unshift()` | Add element(s) to start of `arr` | `element1`*[*`, element2, ..., elementN`*]* | Updated `arr.length` value | [Array.prototype.unshift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) |
| `.shift()` | Remove first element from `arr` | (no parameters) | The element removed from `arr`, or `undefined` if `arr.length === 0` | [Array.prototype.shift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) |
| `.slice()` | Extract element(s) from `arr` | *[*`start, end`*]* | A new array containing the element(s) extracted from `arr` (`arr` is not changed) | [Array.prototype.slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) |
| `.splice()` | Remove and/or replace element(s) from/in `arr`  | `start`*[*`, deleteCount, item1, item2, ..., itemN`*]* | A new array containing the removed element(s) (if applicable), or an empty array if no element was removed (`arr` is modified) | [Array.prototype.splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) |
| `.find()` | Returns the first-encountered value in `arr` | `cb`(`element`*[*`, index, array`*]*)*[*`, thisArg`*]* | The value of the first element found via `cb(...)`, otherwise `undefined` if not found | [Array.prototype.find()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find) |
| `.findIndex()` | Returns index of the first-encountered value in `arr` | `cb`(`element`*[*`, index, array`*]*)*[*`, thisArg`*]* | The index of the value of the first element found via `cb(...)`, otherwise `-1` if not found | [Array.prototype.findIndex()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex) |
| `.forEach()` | Performs an action on each element of `arr` | `cb`(`currentValue`*[*`, index, array`*]*)*[*`, thisArg`*]* | `undefined` (`arr` is not changed by `.forEach(...)`, but can be changed by `cb(...)`) | [Array.prototype.forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) |
| `.map()` | Maps an action on each element of `arr` to a new array | `cb`(`currentValue`*[*`, index, array`*]*)*[*`, thisArg`*]* (where `cb(...)` `return`s the new value of each element) | The new array, as mapped by `cb(...)` (`arr` is not changed) | [Array.prototype.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) |
| `.filter()` | Filters `arr` on a test condition to a new array | `cb`(`element`*[*`, index, array`*]*)*[*`, thisArg`*]* | The new array, as filtered by `cb(...)`, or an empty array if all elements fail the test in `cb(...)` (`arr` is not changed) | [Array.prototype.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) |
| `.reduce()` | Reduces `arr` to a new single value | `cb`(`accumulator, currentValue`*[*`, currentIndex, array`*]*)*[*`, initialValue`*]* | The new value, as reduced by `cb(...)` (`arr` is not changed) | [Array.prototype.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce) |

*(N.B. In the table above, **optional parameters** are indicated with* [...] *, and* `cb`(`...`) *denotes an arbitrary **callback function**.)*

Some examples of using these array methods are as follows:

```js
// TO-DO: CODE EXAMPLES
```
In the case of array objects, there can be arbitrarily many such (independent) array objects in a given program, called **instances**, each having their own corresponding `length` property and methods (e.g., `.pop()`, `.map()`, etc.). Such properties and methods are therefore called **instance properties** and **instance methods**. Conceptually, these object instances “live” independently in the program as long as they are in scope:

**!TO-DO FIGURE**

#### ***Aside***: Wrapper Objects

Note that JavaScript also provides **wrapper objects** to convert primitives into corresponding objects with associated properties and methods (e.g., `.toString()`, `.valueOf()`, `.parseInt()`, `.isNaN()`, etc.)---i.e., `String`, `Number`, `BigInt`, `Boolean`, and `Symbol` (`null` and `undefined` do not have corresponding wrappers). The primitives are still implemented (i.e., rather than using these wrapper-object representations by default), however, for the aforementioned performance reasons (recall Section F-4). See [MDN]( https://developer.mozilla.org/en-US/docs/Glossary/Primitive#Primitive_wrapper_objects_in_JavaScript) for further discussion regarding primitive wrapper objects.

#### Objects in the Global Scope

Additionally, the JavaScript runtime environment also provides several useful **objects** that are accessible in the **global scope** of a program. While a comprehensive review of these objects is beyond the scope of discussion, consider the `Math` object as a representative “case study.” The `Math` object can be represented by the following abbreviated diagram (see [MDN]( https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) for full reference of the `Math` object):

<p align="center">
<img src="https://github.com/awpala/programming-primer/blob/master/images/12-F5-MathUML.JPG" alt="pseudo-UML diagram for Math object")
 </p>

A few illustrative examples of using the `Math` object are as follows:

```js
// TO-DO: CODE EXAMPLES
```

*(N.B. See [MDN]( https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects) for the full reference list of available built-in objects in the global scope.)*

#### ***Aside***: Instance Objects vs. Static Objects

As a point of additional note, recall the aforementioned array object’s `length` property and various methods (e.g., `.pop()`, `.splice()`, etc.) were specific to each individual *instance* of an instantiated array object, and are correspondingly referred to as **instance properties** and **instance methods**, respectively. Conversely, there is only a *single* `Math` object provided in the global scope by the JavaScript runtime environment (e.g., the property `Math.E` represents the mathematical constant *e*, Euler's number). Thus, rather than instantiating *multiple* instances, the *single* `Math` object is used directly in expressions, with its members being accessed correspondingly as `Math.property` and `Math.method()`. The properties and methods of the `Math` object are therefore denoted **static properties** and **static methods** (respectively) to distinguish this accordingly (i.e., using a *single* "static" `Math` object which returns values directly, rather than declaring "instances" `Math1`, `Math2`, `MathC`, etc.).

#### The `console` Object

Another “object” of note is the `console` object, which is similarly provided by the JavaScript runtime environment (via API) and accessible in the global scope, providing the corresponding familiar method `console.log()` (among others; see [MDN]( https://developer.mozilla.org/en-US/docs/Web/API/console) for full reference of the `console` object).

#### The Document Object Model (DOM)

As a final point of discussion, consider the **Document Object Model (DOM)**, which is a hierarchical representation of a Web page's structural content. Recall that the primary application domain of JavaScript is the development of Web software applications. Accordingly, the DOM provides an **interface** with which JavaScript can interact with the content of a Web page and confer functionality on it.

*(N.B. The DOM is not formally specified in the ECMAScript language specification, however, the DOM is largely [standardized](https://dom.spec.whatwg.org/) across Web browsers to promote the portability of Web applications. Accordingly, the corresponding browser-implemented JavaScript runtime environments provide a **[Web API](https://developer.mozilla.org/en-US/docs/Web/API)** to allow for interaction with the Web page content (including the DOM) via JavaScript, thereby enabling the ability to create functional Web applications.)*

In JavaScript (i.e., via the Web API), the DOM is modeled as an object called `document`, having corresponding properties and methods.

**!TO-DO FINISH DOM CONTENT**

[:arrow_up_small: Return to top](#overview)

## G. JavaScript Programming: A Guided Example

**!TO-DO**

[:arrow_up_small: Return to top](#overview)

## H. Program Errors

**!TO-DO**

[:arrow_up_small: Return to top](#overview)

## I. Key Takeaways

**!TO-DO**

[:arrow_up_small: Return to top](#overview)

## J. References

**!TO-DO**

[:arrow_up_small: Return to top](#overview)
