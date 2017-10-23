# Logical Systems

### Based on MIT 6.004 Basics of Information Systems

## Information

Information is knowledge which resolves uncertainty

I(x<sub>i</sub>)=log<sub>2</sub>(1/p<sub>i</sub>)

Example: Information on one coin flip = 1 bit, while information from 2 dice = 5.2 bits

Information Entropy is expected information from each value.
H(X)=E(I(x<sub>i</sub>))=summation of possibilities (probability * log<sub>2</sub>(1/p<sub>i</sub>) )

What matters in Encoding:
- Mechanism  with Devices and Components
- Efficiency with Bits Needed
- Reliability with Immunity to Noise
- Security with Encryption

Encoding:
- Huffman algorithm when not all bits are equally probable
- Encode multiple bits at same time for increased compression

## Boolean Representation
- Truth Table
- Min/max term notation
- K-map
- Boolean expressions and gates

## Physical Implementation
- Noise margins
- Static Discipline
- CMOS transistors, gates, timing

## Synthesis
- Minimization
- muxes
- ROMS