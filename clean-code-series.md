# Clean Code
While at Pixo, the developers watched and discussed [Uncle Bob's](http://blog.cleancoder.com/) [Clean Coders](https://cleancoders.com/) video series.

**Disclaimer:** these are my _very_ rough notes.

## Episode 2 – Naming things
- Variable and function names shouldn't need comments. :: bad code smell that you aren't clearly conveying your meaning
- Names shouldn't spread dis-information.
- Names should be pronouncable.
- "Names are not just for convenience, they are used for communication"
- "Variables and Classes are nouns.  Methods are verbs or verb phrases.  Booleans should be predicates.  Enums are often adjatives."
- Avoid encodings
- "Any fool can write code a computer can understand, but it takes a good programmer to write code humans can understand" - Martin Fowler.

## Episode 3 – Functions
- Keep methods short.
- Familiar landscapes offer comfort, but organization schemes for individuals are not a good paradigm for team situations.
- "I'm sorry this letter is so long.  I didn't have time to make it shorter" - Pacal
- enables better readability.
- "Large functions are where classes go to hide"
- if a function deals with more than one level of abstraction, it's doing more than one thing and is too long.
- "Extract till you drop"
- Small, well named functions act like signposts.

## Episode 5 – Form
- The code should be the documentation for your comments.  They shouldn't be documented separately
  - Might work for smaller teams (< 10 people or so), but actually documenting coding standards is better as # of programmers grows... Unless you use some kind of standard adherence tool.

## Episode 6a – Test Driven Development
- Red → Green → Refactor → Repeat
- Uncle Bob's 3 laws
  1. Write NO production code except to pass a failing test.
  2. Write only enough code of a test to demonstrate a failing test.
  3. Write only enough production code to pass the test.
- Writing tests after you have working code removes incentive to write complete coverage and introduces holes.
- Decouple code improves design and testability
- “Tests eliminate the fear to clean code”

Skipped from 21:30 to end

- Tests are like double entry book keeping done by accountants.

I can see how it can be slow to transition to TDD, but I don't need convincing of its worth.

1. Unit Tests > Integration tests
2. coverage analysis tools?

## Episode 7 – Architecture, Use Cases, and High Level Design
- TOC: Use cases, MVC & other partitioning methods, framework binding.
- Architecture exposes usage
- Good architecture allows you to postpone decisions. (Databases, UI, Service lays, frameworks, …)
  - Fitness project: WikiPage was central focus surrounded by the business objects.
  - Focus architecture on “Use Cases”
- Use Cases expose intent.  (same as “User stories”?)
  - A use case is a formal description of how a user interacts with the system to achieve a goal.
- Partitioning:
  - Application objects, Interactor objects
- Database

## Episode 8 - S.O.L.I.D. Overview

### 11:14: The source code is the Design
- The cost of building is the cost of compiling.
- The cost structure is inverted compared to physical anologs. (Houses, circuits, etc…)
- It’s easy to evolve a system into something that works well, or a burning mess

### 20:00: Bad Design Smells
- Regidity
  - Long build & test times = rigid systems
  - Sign of coupling
- Fagility
  - Long distance dependencies
- Immobility
  - Components cannot be easily extracted and reused.
- Viscosity - Necessary operations are difficult to perform and take a long time to execute.
  - Irresponsible tolerance to bad decisions
- Needless Complexity
  - Anticipating 

### 30:30 Code Rot

### 37:00 What is OO
- Dependency inversion - Dependency opposes flow of control
- dynamic polymorphism
- Essential quality: ability to invert key relationships, isolate high level policies from low level design
- Interfaces

### 46:45: Dependency Management
- [Single Responsibility Principle](https://en.wikipedia.org/wiki/Single_responsibility_principle)
- [Open/Close Principle](https://en.wikipedia.org/wiki/Open/closed_principle)
  - Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.
- [Liskov Substitution Principle](https://en.wikipedia.org/wiki/Liskov_substitution_principle)
  -  if S is a subtype of T, then objects of type T may be replaced with objects of type S without altering any of the desirable properties of that program.
- [Interface Segregation Principle](https://en.wikipedia.org/wiki/Interface_segregation_principle)
- [Dependency Inversion Principle](https://en.wikipedia.org/wiki/Dependency_inversion_principle)

### 48:45: Conclusion

## Episode 9 - Single Responsibility Principle
* 1:00 - overview
* 3:50 - Science lesson (General Relativity)

### 10:00 - Responsibility
- "The best modules are those that have just 1 responsibility."
- Who is the audience for a method?  Which users will request changes to the responsibility?
- what are the responsibilities to the different groups of users you serve?
- Separate users/actors.
- Responsibility is a family of functions that serve a single actor.

### 16:20 - The Two Values of Software
- Primary: the software is easy to change.
- Secondary: behavior meets users needs.

Friction
- minimize responsibilities in a class
- co-location is coupling
- couplings tend to accumulate over time, which leads to fragility

### 27:50 - SRP
when responsibilities are kept separate, your plug becomes more plug-able.
causes:
- pull code into separate source files
- extract methods
- merge single functions into classes, classes into modules

### 41:15 - Solutions
- Invert Dependencies
- Extract Classes
- Facade pattern
- Interface Segregation
- "Perfect solutions are for fiction writers and mathimitions."

### 48:00 - Case Study
- "Unit tests tend to keep the same things separate that actors keep separate."
- TDD got me about 80% of the way there.
- "The best time to draw pretty diagrams is when you are done."

### 1:00:00 - Conclusion

## Episode 10 - The Open Close Principle
* 0:50 - Overview
* 4:15 - The Quantum Discontinuity

### 11:42 - Open and Closed
- A software module should be open for extension, but closed for modification"
- Something like passing in an object that conforms to an interface or a base class?

### 20:45 - A Smelly Design
- Smell: immobility

### 35:30 - De-oderizing the Design
- www.github.com/unclebob/Episode-10-ExpenseReport

### 42:45 - The Lie

### 46:50 - Two Solutions
- Big Design Up Front (Large, top-heavy, and anticipatory abstractions)
- Agile Design (Pragmatic & reactive)

### 56:15 - Reprise

### 57:25 - Conclusion
- "The Open Close Principle is at the moral center of system architecture.  To the extent that a system is not open for extension and closed for modification, that system is immoral."

## Episode 11 - Liskov Substitution Principle  (part 1) 
- 1:00 - Recap of Ep 10
- 5:00 - Wave Particle Duality

### 13:18 - Type theory
- What’s in a type - a bag of operations.

### 21:55 - Subtypes
- asymmetry of usability
- "Subtypes can be used as their parent types"

### 34:30 - The representative rule
- Square/Rectangle
- Every refused bequest is a violation of the open-closed principle.
- Solution: keep Squares and Rectangles as separate types.
- Representative do not share the relationships of the things they represent.
	
## Episode 11 - Liskov Substitution Principle  (part 2) 

### 0:15 - Heuristics
- If the base class does something, the derived class must do it too and in the same expected way.
- The derived function unconditionally throws an exception
- isInstanceOf (unless it’s to re-assert information the compiler has lost)
- Type Cases
- Inheritance breeds rigidity, you drag along all the dependencies along with the base class

### 10:20 - Design by Contract

###13:45 - The Modem Problem
- Solution: adaptor class pattern. All Dependencies point away from the ugly hack.

### 27:25 - Conclusion

## Episode 12 - Interface Segregation Principle
- 3:20 - Overview
- 6:55 - Heisenberg Uncertainty Principle

### 14:30 - Interfaces
- Name has more to do with its user than its implementers.

### 24:40 - Fat Classes
- Classes that have lots and lots of methods.  Lots of fan out.
- Issues: longer build/compile time.  strongly coupled dependencies.
- Solution: implement multiple interfaces.
- 36:30 - The ATM Example

### 45:00 - Physical Structure
- Don’t depend on things you don’t need.

### 54:05 - The Need to Know
- "Loose Lips sink ships, and leaky abstractions create distractions."

### 58:20 - Conclusion

## Episode 13 - The Dependency Inversion Principle
- 3:10 - Overview
- 5:55 - Einstein’s Dilemma
- 13:35 - Dependency Inversion Begins

### 22:00 - What are dependencies?
- Run time vs.  compile time.

### 28:25 - Dependency Inversion
- polymorphism 
- divide the system by boundaries, then point dependeces away from those boundaries. 
- modules that contain high level details like business policies should not depend on low level modules that generate html output or report formatting.

### 38:30 - The Inversion
- 41:00 - Dependence Inversion Examples
- 47:40 - Conclusion

## Episode 14 - Solid Summary (Payroll system case study)

### 2:30 - Requirements and Use Cases

### 10:20 - The Single Responsibility Principle

### 13:45 - Diagrams and YAGNI
- YAGNI: You aren’t going to need it.
- Code diagrams usually are rife with rot.
	- All the more reason to automate that?

### 17:30 - The Open-Closed Principle
•	“Notice how conformance to the open-close principle improves conformance to the single responsibility principle”

### 22:05 - The Liskov Substitution Principle
- Special case: null object case

### 28:05 - The Interface Segregation Principle	
- Dynamic factory

### 31:35 - The Dependency Inversion Principle
- Remember: “High level policies should be isolated from low level details”

### 33:35 - Conclusion

### Group Discussion:
- "Start listening for what the client is saying as it will give you clues about what the architecture needs to look like."
- … We all need access to the raw data of the client’s request, because we all form our own filters and views of the client’s request.  Chaining understanding Client > PM/UX > Dev reduces understanding of the problem.

## Episode 15 - Solid Components
- 2:10 - Overview
- 3:45 - White Dwarf Stars

### 9:10 - What is a Component?
- an independently deployable library/module/jar file/gem/etc…

### 21:10 - Coffee Maker Requirements

### 27:10 - The Architect’s solution

### 34:40 - A Real Design

### (45:40 - Implementation)

### 50:55 - Components

### 53:35 - Conclusion
- The code that implements low level details depend on the high level policies, not the other way around.

### Episode 16 - Component Cohesion
- 1:50 - Overview
- 4:15 - Type 1A Supernovae

### 9:50 - Cohesion
- Functions are the basic element
- Classes are the first level of cohesion.
- Common errors:
	- Bundling entire inheritance hierarchies together.
	- Things that use the base class are often bundled together with the base class.  Sub classes should not be bundled with the parent classes.
- Goal: Independent Deployability

### 14:45 - The Release-Reuse Equivalence Principle
- The granule of reuse is the same as a granule of release
- A component needs to be large enough to justify the overhead of managing the release cycle.

### 24:10 - The Common Closure Principle
- Classes that would be changed for the same reasons should be grouped together
- That means that these classes should all serve the same actor.
- They are closed to the needs of every other actor.
- Systems are composed of layers that separate business rules from low level details.  Those layers are partitioned into components.  Each component are composed of classes that serve a single actor

### 31:30 - The Common Reuse Principle
- Group together classes that are used together.

### 41:15 - The Tension Diagram
- These 3 principles work in tension, pulling a system’s design in a different directions.
- Position within the triangle depends on how mature your product is.  Early: common closure & common resuse principle.  Moves towards Release-Reuse principle.

### 46:10 - Conclusion

## Episode 19 - Advanced TDD #1
- 3:50 - Core Collapse Supernova

### 12:50 - TDD Review, The 3 Laws
- Before you write production code, you must first write a failing test.
- Write minimal code to make the test fail.
- Stop writing code as soon as the test passes.
- "Refactoring is like washing your hands after going to the bathroom."

### 32:10 - The single assert rule
- Every unit test should have one and only one assert.
- Arrange, act, assert
- Don’t want the output of one test to be the input of another test.  aka: arrange, act, assert, act, assert, …

## Episode 19 - Advanced TDD #2
- 0:00 - overview
- 1:10 - Incremental Algorithmics
- 24:55 - Getting Stuck
- 36:00 - Getting Unstuck

### 49:20 - Conclusion
- Tests cannot fully constrain a program.
- Tests can only prove a program wrong, not right.


## Episode 20 - Clean Tests
- 5:50 - Overview
- 8:30 - History of the Earth

### 20:50 - Anatomy of a Test
- Arrange, Act, Assert, Annihilate

### 29:50 - The Arrange
- Drives the system into a testable state
- The "Test Fixture"

**(31:00)** Approaches to managing fixtures:

1. Transient Fresh - Created and destroyed around every test.
2. Persistent Fresh - Survives from test to test.  Allows state to accumulate from test to test.
3. Persistent Shared - 

**Convention:** initialize fixtures in setup() methods

### 40:55 - Setup Struggles

### 52:55 - Test Hierarchy
- Ruby Rspec
- Contexts have their own before/after stuff
- Replicating in other languages: nest test classes, and make them inherit from their parent containing class.

### 1:06:00 - Clean composition
- Group a series of actions together into a (utility) function so it looks like you are only calling one action.
- The single assert principle means there should only be one logical assertion.  You can have multiple assert statements, just not a series of Act-Assert pairs.

### 1:21:00 - Conclusion

## Episode 21 - Test Design Study.

### 3:20 - Test Location
- Folder for tests vs. Test files alongside corresponding production files.
### 8:10 - Test Files
- 1 Test file per class*:
	- Interfaces don’t have tests.
	- Inner classes get their own file
	- Classes created out of a refactoring don’t often get tests (assuming the source code already has tests)
- Test Suites

### 15:25 - SOLID tests.
- Open Closed principle: Hide internal details from tests by passing in values needed to construct objects rather than constructing those objects within your tests.  This helps the rest of your code too.
- "Tests are just another form of client"
- Testing Private functions.  Find a way to test them through public functions.  If you have to test it, you can’t hide it in a private function

### 31:30 - Test Location
- "Some experienced TDD’ers will write out a list of tests they think they will need to pass."  Planning will be continuous.
- Behavior driven development: Given - When - Then,  name tests for the action & assertion (when - then)
- We want the tests to remind us what the requirements are.  The names should reflect the requirements, not the implementation.

### 51:00 - Conclusion
- Follow whatever pattern your IDE follows.
- We don’t test classes, we test behaviors.

## Episode 22 - The Process of Writing Tests.
- 0:45 - Overview
- 3:45 - The Great Galaxy Debate

### 10:45 - Simple Techniques
- "Fake it ‘till you make it" - The goal is incrementalism
- "Stair Step Tests" - Tests whose sole purpose is to allow you to write the next test in sequence.  Once you write that test, the stair step test can be deleted.
- "Assert First" - Start with the assert first.

### 31:45 - Triangulation
- Remember, as the tests get more specific, the code gets more generic.
- Savings accounts > Money market account > extracted base class
- "One to Many" : start with one object (singular situation) and work towards many (plural situation)

### 53:10 - Refactoring Tests
- The 2 disk problem - it’s better to loose your production code because you can recreate it from the test suite.  You can’t practically recreate the test suite from the production code.
- "The best tests read like well written specifications."

### 1:03:55 - Tests are specifications
- "Write the tests you would want to read"
- "Test the behavior, not the API."

### 1:10:10 - Tests Come First

Ron Jeffries’ rules of simple design

1. "First, the code has to pass all it’s tests"
2. "no duplication"
3. the code should express all ideas the author wants to express
4. Minimize classes and methods

Kent Beck says:

1. Make it work
2. Make it right
3. Make it fast & small

- “In all things, the tests come first”
- Optimize last.

### 1:18:05 - Conclusion

