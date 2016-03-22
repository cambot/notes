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
