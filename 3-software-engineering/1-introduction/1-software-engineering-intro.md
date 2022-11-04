# Introduction to software engineering

* As sophisticated as programs are going to get, all programming fits in a very simple mental model of inputs and outputs.

* You just have to recognize the vocabulary and to know what kinds of puzzle pieces or concepts ultimately to apply.

* If you take your vision and componentize it into smaller, bite-sized problems, you can take these baby steps and solve everything collectively.

* Keep in mind the idea of reusable code. Instead of constantly copying and pasting, reusing code would not just give you correctness but also a better design.

## Separation of Concerns

* <https://en.wikipedia.org/wiki/Separation_of_concerns>

* <https://www.d.umn.edu/~gshute/softeng/principles.html>

* Separation of concerns is a recognition of the need for human beings to work within a limited context.

* A programmer is having to do several things at the same time:
    1. Describe what is to be computed.
    2. Organise the computation sequencing into small steps.
    3. Organise memory management during the computation.

## Modularity

* Following the principle of modularity implies separating software into components according to functionality and responsibility.

## Abstraction

* Following the principle of abstraction implies separating the behavior of software components from their implementation.

* It requires learning to look at software and software components from two points of view: what it does, and how it does it.

* Design by contract `DbC` is an important methodology for dealing with abstraction.

### Design by contract

* It prescribes that software designers should define formal, precise and verifiable interface specifications for software components, which extend the ordinary definition of abstract data types with preconditions, postconditions and invariants.

* These specifications are referred to as "contracts", in accordance with a conceptual metaphor with the conditions and obligations of business contracts.

## Anticipation of change

* The principle of acticipation of change recognizes the complexity of the learning process for both software developers and their clients.

* Preliminary requirements need to be worked out early, but it should be possible to make changes in the requirements as learning progresses.

* Coupling is a major obstacle to change. If two components are strongly coupled then it is likely that changing one will not work without changing the other.

* Cohesiveness has a positive effect on ease of change. Cohesive components are easier to reuse when requirements change. If a component has several tasks rolled up into one package, it is likely that it will need to be split up when changes are made.

## Generality

* The principle of generality is closely related to the principle of anticipation of change. It is important in designing software that is free from unnatural restrictions and limitations.

## Incremental Development

* An incremental software development process simplifies verification. If you develop software by adding small increments of functionality then, for verification, you only need to deal with the added portion. If there are any errors detected then they are already partly isolated so they are much easier to correct.

## Consistency

* The principle of consistency is a recognition of the fact that it is easier to do things in a familiar context.

* At a higher level, consistency involves the development of idioms for dealing with common programming problems.

* A consistent look and feel makes it easier for users to learn to use software. Once the basic elements of dealing with an inteface are learned, they do not have to be relearned for a different software application.

* A consistent user interface promotes reuse of the interace components.
