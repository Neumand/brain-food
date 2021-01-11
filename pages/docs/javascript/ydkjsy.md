# You Don't Know JS Yet (2nd Edition ) - Kyle Simpson

## Chapter 1: What  _Is_  JavaScript?

A programmming language that was initially conceived to cater to an audience of Java developers (hence the name).

### Language Spec

**TC39:** The technical steering committe that manages JS. Their primary role is to manage the official specification for the language.

It's comprised of 50-100 people from a broad array of web-invested companies (i.e Mozille, Google, Apple) and device makers.

All proposals go through a 5-stage process (0-4, since we're programmers!). When a proposal reaches Stage 4 it is eligible to be included in the next yearly revision of the language.

### Environments

JS has evolved to run in many places, but how it is implemented centers around the web.

Many JS-looking APIs are in fact web APIs that can be used in different environments (i.e `fetch`, `alert`). These envrionments add the APIs into the global scope of your JS programs. Most cross-browser issues that people encounter are due to how these environments work, not how JS itself works.

### Paradigms

**Paradigm**: a broad mindset and approach to structuring code.

Examples:
* Object-oriented (OOP). Organizes code by collecting logic and data together into classes.
* Functional. Organizes code into pure functions.

JS is a multi-paradigm language in the sense that you can make decisions about what kind of paradigm to follow on a line-by-line basis. You're not forced into any approach.

### Backwards and Forwards Compatibility
A foundational principle of JS, code written in 1995 will still be able to run today. Valid JS is valid JS.
> We don't break the web! - TC39

On the other hand, JS is *not* forwards compatible; future additions to the language are not expected to run in an older JS engine. This is why in older JS projects you won't see newer features. They simply wouldn't work in the project.

Transpilation tools such as **Babel** allow developers to use newer features on an older JS engine.

It's strongly recommended that developers use the latest version of JS so that their code is clean and communnicates ideas most effectively.

**Polyfills** are used to add definitions to APIs for missing methods that only exist in newer JS specs. These act as if the older environment already had them defined. Tools like Babel are able to detect which polyfills are needed for your code and fill them in as needed.

### Interpretation
Most people assume that JS is an interpreted or scripting language. In fact, Kyle explains that the answer is more complicated than that.

The fact of the matter is that JS is a **parsed language**; JS code is parsed before it is executed. Parsed and compiled languages are similar in the sense that they are both parsed before the code is generated. In fact, many parsed languages perform code generation and as a result closely resemble compiled languages.

After JS code is parsed it is converted into a sort of binary byte code and subsequently executed.

![Steps of JS compilation and execution](https://github.com/getify/You-Dont-Know-JS/raw/2nd-ed/get-started/images/fig3.svg)
*Steps of JS compilation and execution*

1. Code is transpiled, packed and then delivered to a JS engine
2. JS engine parses the code to an Abstract Syntax Tree (AST)
3. Engine converts the AST to the sort of byte code, which is then refined further by the optimizing Just-In-Time (JIT) compiler
4. JS VM executes the program

**Conclusion**: JS more closely resembles a compiled language than an interpreted one

### Web Assembly (come back to this section)
Web Assembly - or WASM - was created by a group of engineers and based off of a style of code that favored a subset of the JS language: **ASM.js**.

### Strict Mode
**Strict mode** serves as an optional yet recommended way to do things so that the JS engine has the best chance of optimizing and efficiently running the code. Most of these are early errors that are thrown before the code is run.

Some features that strict mode provides:
* Disallows the naming of two function parameters to the same thing
* `this` defaults to `undefined` instead of the global object

As mentioned earlier, since JS is *not* fowards compatible, there is little chance that `use strict` will become the default. It would mean that legacy code running without this mode would no longer work.

### Chapter Summary
* JS is an implementation of the ECMAScript standard and guided by the TC39 committee
* JS is a multi-paradigm language
* JS is a compiled language. The tools process and verify a program before it executes

## Chapter 2: Surveying JS
