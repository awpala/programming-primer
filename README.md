# A Primer on (JavaScript) Programming

## Overview

A brief history of computing and programming, and a general introduction to JavaScript programming

## A. TL; DR

* **Key Point #1**: *The paradigm of transistor-based general-purpose computers, implemented with the von Neumann architecture and running programs written by human programmers in a (more-natural) general-purpose programming language, remains the predominant form of computer programming today.*
* **Key Point #2**: *JavaScript/ECMAScript has come to dominate the Web-application software development arena, and has become a full-fledged, robust general-purpose programming language in its own right since its humble origins as a simple scripting language, all the way through the present day.*

**!TO-DO**

## B. Contents

**!TO-DO**

## C. A Brief History of Modern Computing and Programming

### C-1. Early Era (1800s to 1940s)

Computation has a long, rich history, but its modern form originated approximately in the mid-1800s, with Charles Babbage’s conception of the analytic engine, a mechanical device which (in principle) would behave similarly to what would now be recognized as a general-purpose computer.

Through the turn of the 20th century, several other important developments had been independently discovered, including the formalization of key mathematical logic constructs by George Boole (a body of work now known eponymously as Boolean algebra). This continued progression of events up through the 1920s and 1930s culminated in the work of Alan Turing and his contemporaries. Turing’s canonical paper “On Computable Numbers, with An Application to the Entscheidungsproblem” (1936) formalized the modern notion of “computation”; a corollary of this monumental paper was the ability to precisely specify what is now known as a general-purpose computer.

Building on Turing’s work, and as part of the War effort, the first predecessors of the modern-day computer were conceived and built in the 1940s. The ENIAC is generally regarded as the first stored-program, general-purpose computer to have been built using electronic components (outcompeting its electro-mechanical, electro-magnetic, and other contemporaries); the ENIAC was effectively the first physical manifestation of Babbage’s analytic engine, conceived almost a whole century prior to that point.

These early machines were multi-ton in weight—occupying entire rooms—and had very limited memory and comparatively slow computational speed by modern standards. Furthermore, the binary (i.e., 1/0, or on/off) “language” understood by these machines was programmed using bulky components such as mechanical relays and vacuum tubes, which had performance issues and were susceptible to malfunction.

These implementation difficulties notwithstanding, another important emergent property of these early computers was their fundamental design: the von Neumann architecture. This design (conceived by the mathematical prodigy John von Neumann and his colleagues) formed the basis of all modern computational devices—including the computers, smartphones, etc. in widespread use today.

The von Neumann architecture has the following general structure:

**!TO-DO -- FIGURE**

The structure comprises three key components:
* ***Memory*** - the storage area of the computer, which stores data and instructions of the computer program
* ***Central Processing Unit (CPU), or Processor*** - the “brain” of the computer, which performs computations and reads/writes data and program instructions to/from memory
* ***Input/Output*** - provides a user the ability to interact with the computer

### C-2. Middle Era (1940s to 1970s)

With the groundwork set by these early machines, several problems arose.

There was an obvious impracticality of such large, unwieldy devices which precluded any large-scale manufacture and adoption. A final critical piece was introduced to these nascent “proto-computers” with the invention of the transistor in the 1950s. The transistor is an electronic device which can behave as an “on/off” switch, and is a solid-state device having no moving/mechanical parts. As the manufacturing process of transistors improved over time, the transistor was subsequently incorporated into computational devices to represent the fundamental binary digit (or bit), which underlies all computer hardware. The bit constitutes the simplest possible representation of data in computation: either on, or off. From this fundamental operation, larger, more complex structures such as digital logic gates (based on Boolean algebra) could be built, which ultimately hierarchically form into the full general-purpose computer.

Further innovation in integrated-circuit manufacturing technology over the subsequent decades propelled the transistor into a role of great prominence, as well as sparking the “second westward gold rush” of what eventually would become known today as Silicon Valley. The transistor was critically important in increasing the density of computational power and memory into increasingly smaller physical space (ultimately allowing for the mass production of consumer electronic devices), and it is widely regarded as one of—if not ***the***—most important inventions of the 20th century accordingly.

There was still, however, another problem: the process of “programming” these early computational devices required great skill and was highly tedious and error-prone, inasmuch as these machines were directly programmed in the “native” binary language understood by the machines. These early program were typically printed on punch cards or on tape read by the machine, which required intense labor and skill to write even trivial programs.

A key innovation to address this issue was the development of assembly languages, starting in the late 1940s and into the subsequent decades. Assembly languages use mnemonic terms to represent the binary machine instructions and memory addresses of the computer, alleviating the need to explicitly program the computer in its native binary format.

### C-3. Modern Era (1970s to Present)

While a vast improvement over explicit binary programming, assembly languages did not address several issues which were inherent in writing programs at the time, two of which are of particular note.

Firstly, assembly languages lack portability. A given program written in a given machine’s instruction set (the binary instructions understood by that particular machine) were not directly portable/transferable to another machine—the program would have to be entirely rewritten all over in the new machine’s instruction set in order to execute the same program on the latter machine.

Secondly, writing programs in assembly languages still subjected the programmer to solve problems within the constraints of the machine’s own instructions, rather than solving problems within the constraints of the problem domain itself and in a more natural, human-comprehensible manner. This second issue was ultimately solved with the development of high-level, general-purpose programming languages and their associated compilers in the late 1950s through the 1970s.

A general-purpose programming language allows the programmer to specify instructions in a manner that is more reminiscent of natural language (e.g., English), using descriptive terms to perform operations (e.g., arithmetic, repetitive loops, etc.) and to denote data (e.g., variable declarations), rather than specifying binary machine instructions and binary memory addresses. However, because the computer only understands binary instructions, the compiler (itself a specialized program) servers the role of “translator” from the human’s programming language to the computer’s native binary instructions. Compiler implementations are very complicated and even today are still an active area of research in the computer science arena, however, with decades of innovation preceding them, modern compilers can generate machine code that is approximately just as efficient as that created by a skilled human assembly programmer.

> **Key Point #1**: *The paradigm of transistor-based general-purpose computers, implemented with the von Neumann architecture and running programs written by human programmers in a (more-natural) general-purpose programming language, remains the predominant form of computer programming today.*

Another key innovation was the development of computer networking (i.e., connecting computers into larger, integrated systems), ultimately resulting in the formation of the Internet in the 1980s and the World Wide Web in the early 1990s. (The profound impact of these technologies is readily self-apparent.)

The 1990s and 2000s marked a rapid transformation of globalized society and technology, including the proliferation of many wide-ranging computational devices and consumer appliances. Accordingly, one of the emerging challenges during this time was cross-compatibility of programs and software across these devices (a challenge that still remains today!).

In the mid-1990s, the general-purpose programming language Java was developed by Sun Microsystems to address this issue of cross-compatibility. One of Java’s core tenets was the notion of “write once, run anywhere.” To accomplish this, Java was implemented using a runtime environment (the Java Runtime Environment, including the Java Virtual Machine), which sits on top of each corresponding device’s operating system as a “virtual computer” that provides the ability to translate compiled Java source code (called Java bytecode in its compiled form) into the machine instructions specific to that particular target computer system. (Bytecode is essentially the “assembly program” run by the “virtual computer,” analogously to an assembly program running on the physical computer’s native binary instruction set.)

Java’s popularity grew quickly during this time, and it has since become deeply rooted in the enterprise software development space. Microsoft released the programming language C# (analogously running on top of  the .NET Framework runtime environment) in 2000 as a direct competitor to Java, and many other runtime-environment-based programming languages have also emerged since then.

By the mid-to-late 1990s, as the Web became more prevalent and computers continued to become more powerful, the early form of modern Web applications began emerging. Up to this point, most programmed applications were developed to run in a native format (e.g., desktop applications) targeted to a specific operating system (e.g., Windows, Mac, Unix, etc.). However, with the interconnectivity provided by the Web, it was apparent that applications could similarly be useful in this growing cross-platform, cross-device landscape.

In 1995, Brendan Eich of Netscape developed the JavaScript programming language for use in its Netscape Navigator Web browser application, originally intended as a scripting language based on the Scheme programming language and implemented using an interpreter (analogous to a compiler). Originally slated to be named “LiveScript” in its initial implementation and release, the Netscape team led by Eich elected to name the language “JavaScript” instead, capitalizing on the buzz surrounding its (otherwise unrelated) contemporary at the time, the aforementioned Java programming language.

The ensuing implementation challenges and “browser wars” subsequently to JavaScript’s initial launch and widespread adoption is beyond the scope of the present discussion, however, the key outcome of these events was the standardization of JavaScript’s programming language specification, under the oversight of the European Computer Manufacturers Association (ECMA), which correspondingly named its specification of the language as “ECMAScript” (partly due to trademark infringement concerns with respect to the name “JavaScript”). This is often abbreviated “ES” in reference to modern versions of the language (e.g., “ES6,” the 2015 release of the updated ECMAScript language specification, which marked a critical moment in its maturity as a modern programming language).

Modern implementations (e.g., Google Chrome’s V8 and Mozilla Firefox’s SpiderMonkey engines) of the ECMAScript language specification (i.e., JavaScript) integrate its various features into a single “JavaScript runtime environment,” which provides the ability to program Web applications using the JavaScript programming language targeting the Web browser (e.g., Chrome, Firefox, etc.) as the medium of deployment of the fully functional, standalone Web application. This allows for great portability of Web applications, independently of the user’s operating system (the cross-platform issue is solved by the browser applications themselves, which are generally developed for most major operating systems, e.g., Mac, Windows, and Linux). The proliferation of Web applications from the mid-2000s through the 2010s has largely displaced the use of native desktop applications, and consequently Web applications have become the predominant form of software applications used in practice today.

N.B. [This informative article](https://medium.com/@olinations/the-javascript-runtime-environment-d58fa2e60dd0) provides a more comprehensive review of the various components of the open-source V8 JavaScript engine (Google Chrome’s implementation of the ECMAScript language and runtime engine), as well as the corresponding Web API (not formally part of the ECMAScript language specification) used for DOM manipulation of the Web browser page. V8 was also later adapted by Ryan Dahl to create Node.js, which provides a standalone JavaScript runtime environment allowing to deploy JavaScript applications outside/independently of the Web browser.

> **Key Point #2**: *JavaScript/ECMAScript has come to dominate the Web-application software development arena, and has become a full-fledged, robust general-purpose programming language in its own right since its humble origins as a simple scripting language, all the way through the present day.*

[:arrow_up_small: Return to top](#overview)

## D. The Perfect Language Doesn't Exist :(

With all of the innovations that have occurred in the past century of computation and programming, there are still performance limits of modern computational devices, both in practical and in theoretical terms.

Referring back to the von Neumann architecture model, both processor speeds (i.e., machine operations per unit time) and memory (i.e., total bits of stored information) are finite. Modern computers have processor speeds measured in GHz (billions of operations per second) and memory sizes measured in Gigabytes/GB (billions of bytes of addressable memory, where a “byte” is a conventional grouping of bits into a set of eight). With rapid technological advancements, processor speeds and memory sizes have increased at an exponential rate in the decades spanning from the mid-20th century through the present day. However, while modern applications are far more robust than even as recently as a decade ago, with the explosive growth of devices and data, there are still many applications that even the most advanced computers must contend with.

Furthermore, general-purpose programming languages ultimately become machine-code instructions, and therefore are subject to the constraints of the machine. For this reason, computers in their modern form do not possess “intelligence” and “insight” in the same way that a human does, and are incapable of interpreting ambiguous or unspecific specifications accordingly.

Therefore, an “ideal” computer would be one with infinite processor speed and infinite memory, with the ability to translate ambiguous natural-language specifications directly into a set of precise instructions. This would also obviate the need for computer programmers in the first place (fortunately for programmers, this is not a credible threat!). Interestingly, even if such an “ideal” (read: impossible) machine were available, there are still many mathematical and non-trivial computational problems that are beyond its capabilities!

With these considerations, when a general-purpose programming language is designed and implemented, there are inherent trade-offs that are made accordingly. These typically involve a compromise between high performance (which requires programming “closer to the machine”) vs. readability and expressiveness (which is more similar to natural language, but at the price of more “overhead” to generate the machine instructions from the programmer’s source code resulting in slower performance).

Below is a brief survey of a few representative modern, popular general-purpose programming languages in common use today.

**!TO-DO -- TABLE**

[:arrow_up_small: Return to top](#overview)

## E. What Is a Program?

[:arrow_up_small: Return to top](#overview)

## F. JavaScript Programming: Fundamental Concepts

### F-1. Values, Literals, and Data Types

**!TO-DO**

### F-2. Expressions and Statements

**!TO-DO**

### F-3. Control Structures

**!TO-DO**

#### Conditionals

**!TO-DO**

#### Loops

**!TO-DO**

#### Function Calls

**!TO-DO**

### F-4. Values vs. References

**!TO-DO**

### F-5. Objects and Methods

**!TO-DO**

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
