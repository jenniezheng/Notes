# Logical Systems

## General

Based on [MIT 6.004](https://6004.mit.edu/) Basics of Information Systems

Midterm - One page double sided notes

Final - Two page double sided notes

Roadmap: electrons -> devices -> logic gates -> circuits (EE) -> programmable architecture (CS) -> OS, internet of things

## Information

**Information** is knowledge which resolves uncertainty. Quantify information by optimal bits to store it. Information on one coin flip = 1 bit, while information from 2 dice = 5.2 bits

I(x<sub>i</sub>)=log<sub>2</sub>(1/p<sub>i</sub>)


**Information Entropy** is expected information from each value.
H(X)=E(I(x<sub>i</sub>))=summation of possibilities (probability * log<sub>2</sub>(1/p<sub>i</sub>) )

**Signals** may be discrete/digital or continuous/analog, but are always represented with binary value.

**Static Discipline** says a combinational device has one or more inputs and outputs, a timing specification, and an output specfication

**Voltage Transfer Characteristic** is a V<sub>out</sub> vs V<sub>in</sub> curve.

**Noise** unavoidable problem in circuits. Avoid problems with a safety buffer and V<sub>ol</sub><V<sub>il</sub><V<sub>ih</sub><V<sub>oh</sub>.

**Labels** may be one-hot (array of N-1 zeros and 1 one) or single number in base 2

**Encoding** is a method of effectively storing information with compression. What matters:
- Mechanism  with Devices and Components
- Efficiency with Bits Needed
- Reliability with Immunity to Noise
- Security with Encryption
are
Implementation of Encoding:
- Huffman algorithm when not all bits are equally probable
- Other algorithms when encoding multiple bits at same time

**Decoding** is a method if obtaining stored information. Example: 4->16 decoder converts 4 bits intp 16 bits.

## CMOS Technology
Structure
- MOSFET has bulk, gate, source, and drain
- NFET has + B, - S/D; B should be grounded (pulldown) to remain +.
- PFET has - S/D, + B; B should be connected to VDD (pullup) to remain -.

Complementary MOS
- pullup, pulldown
  - on, off means 1
  - off, on means 0
  - on, on means unknown
  - off, off means no connection
- rising input lead to falling output
    - when all input is 0, PFET on and NFET off so output is 1
    - when all input is 1, PFET off and NFET on so output is 0
    - require inverting logic
    - design for PFET, then swap parallel with series, series with parallel for NFET

Delay
- Propagation Delay P<sub>d</sub> - Upper bound on time for correct output after input changes
- Contamination Delay P<sub>c</sub> - Lower bound on time for output to change after input changes, assumed 0
- Lenient circuit (no glitches) will be valid when any combination of inputs necessary to determine behavior have been valid for P<sub>d</sub>


## Function Specification
Functions can be represented with
- Number Systems
	- Decimal, Binary, Octal, Hex
	- 3 2 1 0 . -1 -2 -> resultant value is a<sup>n</sup>
- Truth Table
- Min/max term notation
- Boolean expressions
    - Operations
    - Or with + | ^
    - And with * V  \&
    - Not with --. !

Functions can be simplified using
- Axioms
	- Identity ( 0 ^ x = 0, 1 V x = 1 )
    - Communitivity 
    - Associativity 
    - Distributivity
    - Idempotence  ( 0 V x = x, 1 ^ x = x )
    - Absorbtion ( x ^ ( x ^ y ) = x ) )
    - Combination ( ( a ^ ( b ^ c )) V ( ~a ^ ( b ^ c ))=  b ^ c  )

- Forms
	- Minterm is a ^ b ^ c
		- gives 1 one and lots of zeros (conjunctive form)
		- product of sums, AND
	- Maxterm is a V b V c
		- gives lots of ones and 1 zero (disjunctive form)
		- Sum of products, OR

- K-map Representation
    - Implicants are areas with all ones
    - Prime implicants aren't completely contained by another implicant
    - Size should be 2<sup>n</sup> wide and 2<sup>m</sup> high
    - 1 or 2 bits = circular array
    - 3 or 4 bits = 2D circular array (useful up to this point)
    - 5 or 6 bits = 3D circular array

## Combinational Logic
Requirements
- All building blocks combinational
- No feedback loops

Basic Blocks
  - NAND and NOR
    - Faster
    - buildable with single CMOS
  - AND and OR
  	- More intuitive

MUX or Multiplexers
- N select lines to one output
- Input on bottom, output on left

-|\\  \
-|&nbsp; |- \
-|/

Decoder
- k select lines to 2<sup>k</sup> output
- Input on bottom, output on right
- Structure of combination ignored, aka glitchy outputs
- ROM or Read-Only-Memory is decoder with only non-variable outputs

&nbsp;&nbsp; /|- \
-|&nbsp; |- \
&nbsp;&nbsp; \\|-

## Sequential Logic

State
- State can be remembered with capacitors
- Voltage stored temperarily in capacitors, must be refreshed every so often because of leakage
- Create feedback loops
- Must be lenient for correct state to be stored

Dynamic Discipline
- T<sub>SETUP</sub>=2T<sub>PD</sub> means input<sub>1</sub> must be stable for setup time before transition of input<sub>2</sub>
- T<sub>HOLD</sub>=T<sub>PD</sub> means input<sub>1</sub> must be stable for hold time after transition of input<sub>2</sub>
