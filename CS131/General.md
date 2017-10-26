# CS131

## General
Book
- Class uses [Webber Online Ppts](http://www.webber-labs.com/mpl/)
- Read Chapters 1-15, 17.

Four types of languages:
1. Imperative - This mainstream language type uses a series of statements to reach a goal
2. Functional / declarative - Founded on mathematics, this language avoids mutations and allows easy parallelism
3. Logic - This language builds upon predicates
4. (Meta) - This language describes other languages

Class covers five specific languages
1. Ocaml - Functional
2. Java - Imperative, Object Oriented
3. Prolog - Logic
4. Python - Mixed
5. Scheme - Functional

Topics
- syntax & semantics
- functions
- types
- control
- objects
- exceptions
- concurrency

Models of Computation
- Finite State machine (FSM) - finite number of states
- Push-down Automaton - FSM with stacks
- Turing Machine - Very simple tape machine than can model any algorithm

## Syntax
Defined as formal grammar. Form independent of meaning. Good syntax should be...
- similar to natural language
- concise
- writable
- readable
- simple
- unambiguous
- redundant

Two seperate grammars
- Phrase grammer is parse tree from tokens (Scanner)
- Lexical grammar is sequence of tokens from text file (Parser)

BNF Grammar
- A Domain-Specific-Language (DSL) for parsing
- Four parts (tokens, non-terminal symbols, start symbol, productions)

Other Grammar Representations
- Extended BNF (EBNF)
- Syntax Diagram with Bypasses, Branching, and Loops

Context
- Context free grammar if all rules are one-to-one, one-to-many, or one-to-none. Aka all rules may be applied no matter the context.
- Context sensitive if application of nonterminal depends on context

Common mistakes in Grammar
- Used nonterminal without definition
- Unused nonterminal with definition
- Infinite loop

Translation
- Tokenize Input
- Type check program
- Check identifiers
- Create intermediate

## Parsing
Parse Terminology
- Parsing - trying to find parse tree for a string. Compilers parse strings using grammar for the specific language.
- Parser - A program that reduces a token sequence to its syntactical
parts, based on a grammar
- Abstract parse tree - An abbreviated parse tree, often with node per operation.

Problems
- Ambiguity
- Associativity (Left or Right?)
- Trade-off between simplicity and readability
- Easy to check a derivation O(n<sup>3</sup>) but hard to find one O(2<sup>n</sup>)

## The System

The Classical Sequence
- Create, compile (and optimize), assemble, link, load, run

Tools vs IDE
- Integrated Development Environments (IDEs) like Spyder or Eclipse highlights errors, debugs, version controls, and compiles
- Tools like those in Unix are more lightweight and customizable. Allows you to customize compilation and optimization, assembling, linking, loading, etc.

Intermediate Languages
- Pure Interpreters (ex: Python interpreter) create intermediate high level language. Points out errors and starts more quickly
- Tokenizing interpreters create intermediate token stream.
- Intermediate-code compiler creates intermediate virtual machine language. Better security, executable on different machines.
- Native-code compiler creates physical machine langauge.
- Just in time compiler (ex: Java compiler) will compile hotspots in code by keeping track of how often bytecodes are used

Profilers
- CPU Profilers will track CPU time of lines
- Memory Profilers like Valgrind will find memory leaks and check memory usage

Static vs Dynamic linking
- Dynamic linking means no need to recompile every time library is changed
- Saves space and compile time
