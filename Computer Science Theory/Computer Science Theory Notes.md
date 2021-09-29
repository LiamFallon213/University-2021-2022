# Computer Science Theory

alt-l for unicode

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


## Sample questions
