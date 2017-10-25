# CS131
### Four types of languages:
1. Imperative - This mainstream language type uses a series of statements to reach a goal
2. Functional / declarative - Founded on mathematics, this language avoids mutations and allows easy parallelism
3. Logic - This language builds upon predicates
4. (Meta) - This language describes other languages

### Class covers five specific languages
1. Ocaml - Functional
2. Java - Imperative, Object Oriented
3. Prolog - Logic
4. Python - Mixed
5. Scheme - Functional

## General Topics
- syntax & semantics
- functions
- types
- control
- objects
- exceptions
- concurrency

## Syntax
Form independent of meaning. Good syntax should be...
- similar to natural language
- concise
- writable
- readable
- simple
- unambiguous
- redundant

## Grammar
##### Parsing
Context Free Grammar - All rules are one-to-one, one-to-many, or one-to-none. All rules may be applied no matter the context.

Parser - A program that reduces a token sequence to its syntactical parts, based on a grammar

Domain-Specific-Language (DSL) - Omits content not within the domain in order to simplify grammar

BNF - A DSL for parsing

Easy to check a derivation O(n^3) but hard to find one O(2^n)

##### Common mistakes in Grammar
Used nonterminal without definition

Unused nonterminal with definition

Infinite loop

##### Translation
- Tokenize Input
- Type check program
- Check identifiers
- Create intermediate

##### Models of Computation
Finite State machine (FSM) - finite number of states

Push-down Automaton - FSM with stacks

Turing Machine - Very simple tape machine than can model any algorithm

##### Tools vs IDE
IDE like Spyder or Eclipse highlights errors and helps with compilation

Tools like those in Unix are more lightweight and customizable

##### Compilers vs Interpreters
Compilers (ex: C compiler) allow for optimization of code and faster execution time

Interpreters (ex: Python interpreter) point out errors and starts more quickly

Just in time compiler (ex: Java compiler) will compile hotspots in code by keeping track of how often bytecodes are used

##### Profilers
CPU Profilers will track CPU time of lines

Memory Profilers like Valgrind will find memory leaks and check memory usage

##### Static vs Dynamic linking
Dynamic linking means no need to recompile every time library is changed
