Febrauary 17th, 2023

### Mealy Machine

A *Mealy Machine* is a 6-tuple $M = \left ( Q, q_0, \sum, \Gamma, \delta, \lambda \right)$. $\Gamma$ is the output alphabet, and $\lambda$ is called the output function. The important thing about Mealy Machines is that each transition outputs a value. $\frac{a}{b}$ represents the transition and output, with $a$ being the transition and $b$ being the output value.

![example](images/mealy.png)

### Moore Machine

Related to *Mealy Machines* are *Moore Machines*. These are defined identically to *Mealy Machines*, except the output values are associated with states rather than transitions.
![example](images/moore.png)

Importantly, all *Mealy Machines* can be converted to *Moore Machines*.

### Pumping Lemma for Context-Free Languages

If $A$ is a  context-free language, then there is a number $p$ (the pumping length) where, if $s \in A \ni |s| \geq p$, then $s$ may be divided into 5 pieces $s = uvxyz$, satisfying the following conditions:

1. For each $i \geq 0, \thinspace uv^ixy^iz \in A$
2. $|xy| > 0$
3. $|vxy| \leq p$ 

![examples](images/pumping_lemma.png)

$0^n$ is a regular language, $0^n1^n$ is not regular but it is context-free. However, $a^nb^nc^n$ is neither regular nor context free. So what is it?

$a^nb^nc^n$ is called turing, or rather can be modeled on a Turing Machine. 

Here is the proof for why $a^nb^nc^n$ is not context-free:
![examples](images/cfl_proof.png)

### Deterministic Pushdown Automota

A DPDA is a PDA with exactly 1 transition per input symbol at any given state. An example would be the automota that recognizes the language $0^n1^n$. An example of an non-deterministic PDA is the automota that recognizes the language $\{L = a^ib^jc^k \thinspace | \thinspace i=j \lor i = k\}$.

A use case of DPDA is determining if a language has an ambiguous grammar or not.

If $L = L(P)$ where $P$ is some DPDA, then L is an unambiguous grammar.