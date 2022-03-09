# Don't repeat yourself

is a principle of software development aimed at reducing repetition of software patterns,replacing it with abstractions or using data normalization to avoid redundancy.

The DRY principle is stated as "Every piece of knowledge must have a single, unambiguous, authoritative representation within a system". The principle has been formulated by Andy Hunt and Dave Thomas in their book The Pragmatic Programmer.

When the DRY principle is applied successfully, a modification of any single element of a system does not require a change in other logically unrelated elements. Additionally, elements that are logically related all change predictably and uniformly, and are thus kept in sync. Besides using methods and subroutines in their code, Thomas and Hunt rely on code generators, automatic build systems, and scripting languages to observe the DRY principle across layers.

## WET
The opposing view to DRY is called WETcommonly taken to stand for "write everything twice"(alternatively "write every time", "we enjoy typing" or "waste everyone's time"). WET solutions are common in multi-tiered architectures where a developer may be tasked with, for example, adding a comment field on a form in a web application. The text string "comment" might be repeated in the label, the HTML tag, in a read function name, a private variable, database DDL, queries, and so on. A DRY approach eliminates that redundancy by using frameworks that reduce or eliminate all those editing tasks except the most important ones, leaving the extensibility of adding new knowledge variables in one place. Kevin Greer named and described this programming principle.

## AHA
Another approach to abstractions is the AHA principle. AHA stands for "avoid hasty abstractions", 
, described by Kent C. Dodds as optimizing for change first, and avoiding premature optimization.[ and was influenced by Sandi Metz's "prefer duplication over the wrong abstraction".


# Rule of three (computer programming)

Rule of three ("Three strikes and you refactor") is a code refactoring rule of thumb to decide when similar pieces of code should be refactored to avoid duplication. It states that two instances of similar code do not require refactoring, but when similar code is used three times, it should be extracted into a new procedure. The rule was popularized by Martin Fowler in Refactoring[1] and attributed to Don Roberts.

**Duplication** is considered a bad practice in programming because it makes the code harder to maintain. When the rule encoded in a replicated piece of code changes, whoever maintains the code will have to change it in all places correctly.


# You aren't gonna need it

"You aren't gonna need it" (YAGNI) is a principle which arose from extreme programming (XP) that states a programmer should not add functionality until deemed necessary. XP co-founder Ron Jeffries has written: "Always implement things when you actually need them, never when you just foresee that you need them." Other forms of the phrase include "You aren't going to need it" (YAGTNI) and "You ain't gonna need it" (YAGNI).


YAGNI is a principle behind the XP practice of "do the simplest thing that could possibly work" (DTSTTCPW).[2][3] It is meant to be used in combination with several other practices, such as continuous refactoring, continuous automated unit testing, and continuous integration. Used without continuous refactoring, it could lead to disorganized code and massive rework, known as technical debt.[citation needed] YAGNI's dependency on supporting practices is part of the original definition of XP.

# Minimum viable product

A minimum viable product (MVP) is a version of a product with just enough features to be usable by early customers who can then provide feedback for future product development

A focus on releasing an MVP means that developers potentially avoid lengthy and (ultimately) unnecessary work. Instead, they iterate on working versions and respond to feedback, challenging and validating assumptions about a product's requirements

Purposes
- Be able to test a product hypothesis with minimal resources
- Accelerate learning
- Reduce wasted engineering hours
- Get the product to early customers as soon as possible
- Base for other products
- To establish a builder's abilities in crafting the product required
- Brand building very quickly

Notable quotes

Steve Blank: "You’re selling the vision and delivering the minimum feature set to visionaries, not everyone

Testing

Testing is the essence of minimum viable products.  MVP seeks to test out whether an idea works in market environments while using the least possible expenditure. This would be beneficial as it reduces the risk of innovating (so that enormous amounts of capital would not have to be sacrificed before proving that the concept does not actually work)


resources 

[Don’t Repeat Yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)

[Rule of three](https://en.wikipedia.org/wiki/Rule_of_three_(computer_programming))

[You aren't gonna need it](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it)

[Minimum viable product](https://en.wikipedia.org/wiki/Minimum_viable_product)
