# Computer Science Theory

*Keybinds*
>alt-l for unicode  
>ctrl-shift-m for preview

## <a href="https://www.cs.montana.edu/yaw/teaching/338/main.html"> Course Schedule & syllabus </a>

---

###  <a href=http://www.jflap.org/> JFLAP software </a>
## 8-31-2020
Makes automata digitally
<br>

 > TA: **Danial Laden**
 Office hours: Wednesday 8:00 - 10:00 am in Barnard 259

### Finite state machine


#### Deterministic Finite Automata (DFA)
> **Deterministic**: The same input always results in the same events or outcome.

An example of a DFA is a Cellular Automata.

##### Characteristics of a DFA
* A single start states
* Multiple accept states
* Reject states (not accept states)
* DFA's either accept or reject strings

##### DFA String Processing
<br>

1. Start at start state

2. Select first character in string
3. Update state by following transition that corresponds to character
4. Select next character in string
5. Repeat 3 & 4 until end of string.
6. If final state is accept state, accept, otherwise reject

##### DFA rules
1. Finite set of states, **Q**
2. Finite alphabet, **∑**
  * Consists of transition characters (i.e. the characters in the strings that the DFA processes)
3. Transition function, **𝛿: Q X ∑ -> Q**
 * **𝛿: Q X ∑ -> Q** means that every state needs to handle every element of the alphabet, (every possible input), exactly one time. No contradictions.
4. Start State **q<sub>0</sub> ∈ Q**
5. Set of accept states, **F ⊆ Q**

##### Definitions
> The set of all strings a DFA, *M*, accepts is called its **Language**, *L(M)=A*
M **recognizes** A

>A language is **regular** if some DFA recognizes it.
*How do you prove a language is regular:* build a DFA for it

---
## 9-2-21

Send bad ideas to purgatory

---

## 9-14-21

### Regular Exceptions

- X* means any number of X's including 0.

 - (xy)* = any number of copies of xy


- X<sup>+</sup> = one or more X's

 - (XY)<sup>+</sup> = one or more (XY)'s

 - Concatanation works like implicit multiplicatior or iuses hollow dot like dot product.

 - U = or

 - ∩ = And

 ---

 # 9-16-21

 ## Project 1

 ### Build State machine of gumball machine

States:
- Has Quarter
- No Quarter

Actions (transitions):
- insertQuarter
- removeQuarter
- turnCrank

## DFA/NFA Limitations

If all regular languages have property ***P***, and some new language ***L*** does not have ***P***, then ***L*** is not a regular language.

- All **finite** languages are regular

  - You can build a DFA for each individual string in the languages  


- All **non regular** languages are **infinite**

- Finite Automata's (FA's) can not process **infinite** strings
- **Arbitrarily** long strings are acceptable

Languages where all strings have bounded size (each string has size <= n for some size n) are regular

## Non regular languages

### Must

- be infinite

- have arbitrarily long strings



## Regular Language Properties
Given a regular language *L*, ∃ a number *p* such that **any** string s ϵ *L* with | s |  ≥ *p*, can be divided into three pieces, *s=xyz* satisfying:
1. x y <sup>i</sup> z ϵ L, ∀ i ≥ 0
2. | y | > 0
3.  | xy | ≤ p

To prove language is not regular, you must prove there is no xyz that can fulfill the pumping lemma.

1. Suppose language is regular
2. Select *p* from pumping lemma
3. Carefully select string ϵ *L*, and | *s* | ≥ *p*
4. Determine what *y* must consist of
5. Make new string by selecting an *i*


# 9-21-21

## Pumping lemma

> Given a regular language *L*, ∃ a number *p* such that **any** string s ϵ *L* with | s |  ≥ *p*, can be divided into three pieces, *s=xyz* satisfying:
1. x y <sup>i</sup> z ϵ L, ∀ i ≥ 0
2. | y | > 0
3.  | xy | ≤ p

- A property that every regular language Has

### Non Regularity Proofs

1. Suppose language is regular
2. Select *p* from pumping lemma
3. Carefully select string ϵ *L* and | *s* | ≥ *p*
4. Determine what *y* must consist of
5. Make new string by selecting an *i*
6. Show new string is not in language

Assume language is regular, show it breaks pumping lemma, contradiction ∴ irregular

#### Example 1
> Claim: the language *L*={0<sup>n</sup> 1<sup>n </sup>:n ≥ 0} is not Regular    
>
>Proof: Suppose *L* is regular. Let *p* be the number from the pumping lemma.
>   
> Consider s=0<sup>p</sup>1<sup>p</sup>.  
> Since *s* ϵ *L* and |s| ≥*p*, the conditions of the pumping lemma must hold for *s=xyz*  
>
> y=0<sup>k</sup> for some k > 0 since Y must exist in the first P characters and the first P characters = 0.                   
>
> s=[0<sup>p-k</sup>][0<sup>k</sup>][1<sup>p</sup>]=[x y z]  
> s'=[x y<sup>2</sup> z]  
s'= [0<sup>p-k</sup>][0<sup>k</sup>]<sup>2</sup>[1<sup>p</sup>]
>  
>  n<sub>0</sub>=n<sub>1</sub>  
n<sub>0</sub>=|x|+|y|+B  
n<sub>1</sub>= |z|-B  
n<sub>0</sub>+|y|=n<sub>1</sub> // Added one Y from pumping lemma  
|y|=n<sub>0</sub>-n<sub>1</sub>  
|y|= 0, |y|≠0  // |y| must not equal 0 by the pumping lemma  
|y|≠|y|  
∴
>  
contradiction

How to do Proof
1. Select *s* that will work with *s* ϵ *L* and |*s*| ≥ *p*
2. Find some conditions that *y* must meet
3. Select an *i*, (Number of times to repeat *y*)
4. Show what *s*' equals
5. Show *s*' is not in *L*

**Pumping lemma TLDR:**

Pick a number less then the length of the string, p.
Split some string into 3 sections x,y,z where only Y must exist. X and Y have to happen before P. Now pick a good y that when repeated takes the string out of the language.

If there is no *i* that pushes the string out of the language, pick a new string.

---

# 9-21-21

- it is possible to pick bad s's

---

# 9-28-21

- Can assume anything proven in class or on homeworks
- 5 questions

  - show language is Regular

  - show one is not regular x2
  - conceptual questions
- One thing to bring for notes is the exact text for the pumping lemma

---
# 10-5-21
## Computational Models
- DFA

- NFA
- PDA (Pushdown Automaton)
  - DFA with a memory stack


- *Turing Machine*

  - DFA with RAM

## Turing machine
- Finite automata with unrestricted memory (RAM / Tape)

- Turing Machine has RAM accessed with a read write head

- Can read from and write to memory
- Can access any spot in memory
- Access to infinite memory (unbounded)
- If it can calculate, it will be done with finite resources
- Start Config: Start State, input on tape, r/w head on the far left
- ∃ states other then accept or reject
- Accept and reject take effect instantly

### TM's consist of
- finite set of states, Q
- Finite input alphabet, ∑(does not include blank symbol)
-  finite tape alphabet, Γ( includes [blank char], ∑ ⊂ Γ)

### TM example
How would you use a TM's tape to see if a string is in the language

L={ a<sup>n</sup>b<sup>n</sup>c<sup>n</sup>: n≥0 }

| a<sup>\\/ | a   | a   | b   | b   | b   | c   | c   | c   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

Memory initial state: input on tape, R/W head at start.
> ω = the current cell

TM M: on input ω
1. if ω = ε accept: otherwise, change first *a* to a 1
| 1<sup>\\/ | a   | a   | b   | b   | b   | c   | c   | c   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
2. Move right to first *b* and change to a 2: reject if c or a null entry found first
| 1<sup>| a   | a   | 2<sup>\\/    | b   | b   | c   | c   | c   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
3. Move right to first *c* and change to a 3, reject if a or *null* is found first
| 1<sup>| a | a | 2  | b | b | 3 <sup>\\/  | c | c |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
4. Move back to first *a*, by finding the character directly following the last 1.
| 1   | a <sup>\\/ | a   | 2   | b   | b   | 3   | c   | c   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
5. Move right to verify not *b* or *c* exist. If so, reject. If not, accept.
| 1   | 1 <sup>\\/ | a   | 2   | b   | b   | 3   | c   | c   |     |     |
| --- | ---------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

</br>Example Tape of Turing Machine</br>

| a<sup>\\/ | a   | a   | b   | b   | b   | c   | c   | c   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |




| 1<sup>\\/ | a   | a   | b   | b   | b   | c   | c   | c   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |


| 1<sup>| a   | a   | 2<sup>\\/    | b   | b   | c   | c   | c   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |


| 1<sup>| a | a | 2  | b | b | 3 <sup>\\/  | c | c |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |


| 1   | a <sup>\\/ | a   | 2   | b   | b   | 3   | c   | c   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |


| 1   | 1 <sup>\\/ | a   | 2   | b   | b   | 3   | c   | c   |     |     |
| --- | ---------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |


| 1   | 1   | a   | 2   | 2 <sup>\\/ | b   | 3   | c   | c   |     |     |
| --- | --- | --- | --- | ---------- | --- | --- | --- | --- | --- | --- |


| 1   | 1   | a   | 2   | 2   | b   | 3   | 3 <sup>\\/ | c   |     |     |
| --- | --- | --- | --- | --- | --- | --- | ---------- | --- | --- | --- |


| 1   | 1   | 1  <sup>\\/ | 2   | 2   | b   | 3   | 3   | c   |     |     |
| --- | --- | ----------- | --- | --- | --- | --- | --- | --- | --- | --- |


| 1   | 1   | 1   | 2   | 2   | 2  <sup>\\/ | 3   | 3   | c   |     |     |
| --- | --- | --- | --- | --- | ----------- | --- | --- | --- | --- | --- |


| 1   | 1   | 1   | 2   | 2   | 2   | 3   | 3   | 3  <sup>\\/ |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ----------- | --- | --- |


| 1   | 1   | 1   | 2   | 2   | 2   | 3   | 3   | 3   | <sup>\\/ |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | -------- | --- |

We have now got a *null* character, exit loop, check for other letters, and accept or reject

Things better then a Turing machine are **Hypercomputers**

Language is Turing recognizable if there is a TM that accepts every string in the language and nothing else

Language is Turing Decidable if it halts on every possible input
---
# 10/7/21
- A<sub>DFA</sub> = <B,ω>
  - <> denotes string encoding of some object
## Decidability
- a *Decidable* language is one which has a decider
  - a decider is a Turing machine that will always halt on a reject state.

>A recognizer is a Turing machine that **Accepts** everything it must accept, and nothing it shouldn't.

>A Decider is a recognizer that also rejects what it doesn't accept.

>A language is decidable if you can make a decider for it.

**Claim:** A<sub>DFA</sub> = {<B,ω>: B is a DFA that accepts string ω} is a decidable language.

**Proof:**
M<sub>1</sub> = on input <B,ω>  
1. Run B on ω
2. If B accepts, accept. If B rejects, reject.


**Claim:** A<sub>NFA</sub> = {\<A>: B is a DFA and L(A)=∅} is decidable.

**Proof:**
M<sub>1</sub> = on input <B,ω>  
1. Run B on ω
2. If B accepts, accept. If B rejects, reject.

# 10/12/21

- Deciders must halt on all inputs

- Deciders must reject everything they don't accept
- Deciders must accept what they are supposed to.

# DECIDERS WE HAVE SOLVED
- ***A<sub>dfa</sub>***
  > A<sub>dfa</sub> = { <M, w> | M is a DFA accepting input w}

  >**Theorem:** A<sub>dfa</sub> is decidable.  
  >**Proof:** We construct a DFA M, deciding A<sub>dfa</sub>.  
  1. Run M on input w.
  2. If M accepts accept, if M rejects reject.

- ***All DFA***
- ***E<sub>dfa</sub>*** (Empty DFA)
>  E<sub>dfa</sub> = { \<M> | M is a DFA and L(M) = Ø }

  >**Theorem:** E<sub>dfa</sub> is decidable.   
 **Proof:** The following machine decides it:  
 >T := “On input  M, where M is a DFA,
 1. Mark the start state of M.
 2. Repeat until no new states are marked in an iteration through all states:
    - Mark any state that has a transition coming from a marked state
 3. If no accept state is marked, accept; otherwise reject.”


- ***EQ<sub>dfa</sub>*** (Equal Language DFA's)
> - Construct DFA C as (A∩B<sup>-1</sup>)U(A<sup>-1</sup>∩B)
  - Run (E<sub>dfa</sub>) on C

- ***Infinite<sub>dfa</sub>***
> - |L(A)| = ∞ ⇔ ∃ loops in A.
  - Loops in A ⇔ A accepts strings ≥ # of states in A.  

  >  M<sub>5</sub> on input \<A>
  1. Let p be the number of states in A
  2. Construct DFA D that accepts strings of all lengths
  3. Construct DFA M where L(M)= L(A) ∩ L(D)
  4. Run E<sub>dfa</sub> on \<M>
  5. if decider accepts reject

# 10/14/21
## Undecidability
### Undecidable problems
### A<sub>TM</sub>

TLDR: If you feed the decider its self everything breaks.
> {\<M,ω>: M is a Turing Machine and M accepts ω (some input)}
> D is the decider for A<sub>tm</sub>
> D<M,ω>
1. if M accepts ω accept
2. reject if M rejects

> - The Set of Turing Machines is Countable (Can be put into correspondence with ℂ (The set of all countable numbers))
> - Claim: The set of all possible Turing machines is countable.
> - Proof: You can order the algorithmic Turing machines in an order and count them  
> All inputs are also Countable  
> Infinite table of all Turing machines of all inputs  
> What is going to happed to D (decider for A<sub>TM</sub>)
> table can't be filled out it is not a decider
> ***THE HALTING PROBLEM** if you feed it it's self, and it accepts, then it rejects, meaning it accepts, meaning it rejects, etc etc

### HALT<sub>tm</sub> The Halting Problem
> Claim HALT: HALT<sub>tm</sub> = {<M,ω>: M is a TM and M halts on ω} is undecidable

>Proof: Suppose HALT<sub>tm</sub> is decidable and let TM H be it's Decider  
>Build a TM that decides A<sub>tm</sub>
>
>  S= on input <M, ω>
  1. Run H on <M, ω>
  2. if H rejects, reject.
  3. if H accepts run M on ω until it halts.
  4. if M accepts, accept, and vice versa
  S is a decider for A<sub>tm</sub>  
∴ HALT<sub>tm</sub> is undecidable

### E<sub>tm</sub>: Empty TM

> Claim: E<sub>TM</sub>{ <M>: M is a TM and L(M)=∅} is undecidable.

>Proof: Suppose E<sub>TM</sub> is decidible and let TM H be it's decider
>
>Build a TM S that decides A<sub>TM</sub>
> S= on input <N,ω>  
>
> 1. Construct TM M2 on input (x):  
> a. if X ≠ ω reject  
> b. if x = ω run N on ω and accept if N does
> 2. Run H on \<M2>.
> 3. If H accepts Reject. If H rejects, accept.

# 10-26-21

Proof: ~~~

Justification: if N accepts w  L(M2) = Σ*. If N does not accept w, L(M2)= ∅. So using H to decide if L(M2) is finite or not determines if N accepts w. Therefore S is a decider for A<sub>TM</sub>, which is a contridiction, so FINITE<sub>TM</sub> is undecidible.

look up what is the church turing thesis



LIST OF THINGS WE HAVE DECIDERS FOR:

EQDFA
INFINITE dfa
ADFA
more

When studying look at the infinite DFA decidible problem.
