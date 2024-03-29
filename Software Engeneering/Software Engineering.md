# Software Engineering

----
## 8-31-2021

### Software development life cycle (SDLC) process

1. Gather requirements
2. Design\
3. Development
4. Testing
5. Deploy
6. Maintenance

### Waterfall Model
Requirements -> Design -> Development -> Testing -> Maintenance

You don't ever go back a step

#### Pros
* Requirements and other previous steps never change

#### Cons
* Inflexible

### Divide and Conquer

Split problem into smaller problems
* Have you seen similar problems before

* Have similar problems been solved before
* Can sub problems be defined
* Can you represent a solution in a manner that leads to effective implementation

### Carry out the plan
* Does the solution conform to the plan

* Is each component part of the solution provably correct
 * Unit Testing: test each individual part

 * Integration testing: test the interactions between parts

### Examine the results
* Is it possible to test each component part of the solution
---
 ## 9-7-21

 ### Homework
 - ok to copy paste definition if sourced

  - Coupling: (definition)

- more resources on prescribed lifecycles
 - Standard Software Development Lifecycles

 - Waterfall Model, Formal Methods, SDLC
 - Provide an exact example for lifecycles

 #### Citations
 EX: "Link: www.stackoverflow.com‎ "

### Lecture
#### Unified Modeling Language (UML)
- Modeling Language

 - Something that describes your system

 - Plain language
 - Psudocode
 - Code
 - Pictures
 - Diagrams
- UML is the Standard modeling Language
 - Helps remove ambiguity


- Software spans from small to extremely complex systems

- UML helps with three questions
 - How do you keep track of which components are needed?
 - What the components jobs are?

 - How are the components communicating with each other?
- There are too many moving parts to developing a large system without help.
| Logical View | Process View |
| ------------ | ------------ |
| **Development View**|**Physical View**|

##### Logical View
- Describes abstractions of a system's parts

- Used to model what makes up a system and how the parts interact
- UML Diagrams in this view tend to be
 - Class

 - Object
 - State Machine
 - Interaction Diagrams
- Gives logical perspective on the system

##### Process View
- Describes the processes and actions inside the systems
- Particularly helpful when visualizing what must happen within your system.

- Usually contains activity diagrams.
- Which actions you need to preform to preform some specific activity
- X -> Y -> Z

##### Development View
- Describes how your systems parts are organized into modules and components.

- Very useful to manage layers within system architecture.
- Typically contains package and component diagrams

##### Physical View
- IRL components
---
# 9-16-21

## Agile Software Development

- The customer is part of the dev team

### SCRUM

- Team is 3-12 members

 - Size is good for resource managment

#### Sprint
- Sprint length 2-6 weeks

- Some time where you have a set goal
- Focused on achiving some goal
- We need to complete X in the next X time period
- Backlog
 - List of tasks

 - Can create a sprint out of backlog
- After sprint then Testing

- Demo to customer
- SCRUM Meeting

- Scope<->Priority<->Estimate
 - Triangle


### Devops

### Devsec ops

---
# 10-7-21 - 11/4/21

## Design Patterns
### Adapter Class
- System 1a and client b

  - Both systems have their own interface

  - Class a and b therefore can't directly interface
  - Create an adapter class works as a bridge between the systems.
###Singleton Pattern
- Each instance contains only a single instance of a Class
 - You have server A,B, & C
 - You have class resources
  - System information class R<sub>1</sub>
    - R<sub>1</sub> ->  CPU = 80%
  - No reason to have more then a single instance of that class, as it can be somewhat a loop, where two end up measuring each other
- Singleton pattern gives us global point of access, like a global variable, but without the downsides.
  - downsides include
    - if it's a large object it could be resource intensive to always have it in scope.

```
public class Singleton{  
      private static Singleton uniqueInstance;
      // other useful instance variables here
      private Singleton();
      public static getInstance(){
        // only works because this is a static function
        if (uniqueInstance == NULL){
          uniqueInstance = new Singleton;
        }
        return uniqueInstance;
        }
        // other useful shit here
      }

}

// call class

Singleton.getInstance();
// on time 1, it makes a new instance, all other times it returns the same instance.
```

```
if (instance does not exist){
  make new instance
} else{
  return existing instance
}
```
### Gumball Machine
  - State diagrams
  -
`---`

### Cyber Security

TESTING STRATAGIES

White box

Integration tests = test how parts work together

Unit testing = test the parts

### Program Analysis

- Node / Basic Block : Largest piece of code that **ALWAYS** executes together

- Represent code as a directed graph of nodes
  - node S := start node
  - node T := end (termanation) nodes
  - Any unique path from S -> T is a possible execution path
  - ep(g) = {All unique paths from S -> t }
  - some paths are infeasable
  - Any loop ⇒ infinite paths

- Node coverage : Statement Coverage

- Edge coverage : Branch Coverage / Flow tesing
 - Try to cover as many edges as possible with a test
 - Better then Node coverage

- Other options
  - All Acyclic paths

  - go through all loops 0 & 1 times
  - *Mc Cabes Criteria*
    - All linearly independant paths

    -  Misses acyclic paths

  - Acyclic paths + 1 run of each loop


- Black Box Testing: testing with no internal access

- White box testing: testing with internal access

### Mutation Testing
 Test the tests

Intentionally make bugs in program, them see if your tests catch them

Differential Testing

-  Test two or more systems that should give same output if given same input, see if <nobr> output = output </nobr>

  - A(x), B(x) if <nobr>A(x) ≠ B(x)</nobr>, something is wrong in either system

  - Only tests one pathway
  - If both are broken in same way tells us nothing
  - Might not have second system

### Metamorphic testing

Find **Metamorphic Relations:** *How your output changes based on the input*.

*O := P(i)* where *P* is some program with input *i*, *O* is defined as the output of *P(i)*

Find  <sup>ΔO</sup>/<sub>Δi</sub>

Check if experimental <sup>ΔO</sup>/<sub>Δi</sub> matches theoretical <sup>ΔO</sup>/<sub>Δi</sub>

∴
