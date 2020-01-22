---
title: "Cohesion In Object Oriented Design"
date: 2019-10-12T00:00:06+02:00
description: "Cohesion in software design is the degree of each elements in a class belongs together."
draft: false
---

Our main topic for this series is **how to write a good software** with these quote
> The good software is high cohesion and loose coupling (Separation Of Concern).


## What is the benefit from writing a good software?

Writing **maintainable, testable and readable** code helps increase productivity for us as a developers. Having highly maintainable code makes it easier to design new features and write code. Modular, component-based, and layered code increases productivity and reduces risk and cost when making changes.

## What is Cohesion?
In software design is the degree of each elements in a class belongs together.

## What is Cohesion types?
1. **Functional cohesion (best)**: This is high cohesion and that mean the class should be self-contained and with a single purpose in other words the class should do one thing and one thing very well. High cohesion is closely related to [Single responsibility principle](https://en.wikipedia.org/wiki/Single_responsibility_principle).

![High cohesion](/posts/images/cohesion/functional_cohesion_high_cohesion.jpg "High cohesion (best)")

* The elements within the object are directly related to the functionality that object is meant to provide. By keeping high cohesion within our code, we end up trying DRY code and reduce duplication of knowledge in our object. We can easily design, write, and test our code since the code for the object is all located together and works together.

* High cohesion give us better designed code that is easier to maintain.

* We cannot always make it perfect, but we can at least strive for it.

* The point is having classes the less elements we have a greate possibility for using them to be used in all the methods.

### Examples:
- Swiss watch each gear/piece SOLID and designed to do one thing.
- Your smart phone you can use one app while installing, updating, and/or uninstalling another! That each app is self-contained is highly cohesive.

### The benefits of high cohesion are:

- **Readability** : (closely) related functions are contained in a single object.
- **Maintainability** : debugging tends to be contained in a single object.
- **Reusability** : classes that have less elements and concentrated functionalities are not polluted with useless functions.

---

2. **Sequential cohesion**: is when parts of a class are grouped because the output from one part is the input to another part like an assembly line (e.g., a function which reads data from a file and processes the data).

![High cohesion](/posts/images/cohesion/sequential_cohesion.jpg "High cohesion (best)")

* Is this case, would there be value in "cutting"  along the dotted line ? not necessarily... can you imagine calling "predict target" without having immediately prior to that called "calculate trajectory" to acquire the information needed by "predict"?  the second task needs the first.

---

3- **Communicational/informational cohesion**: is when parts of a module are grouped because they operate on the same data.

![communicational/informational cohesion](/posts/images/cohesion/communicational-informational-data_cohesion.jpg "communicational/informational cohesion")

![communicational/informational cohesion](/posts/images/cohesion/communicational_cohesion.png "communicational/informational cohesion")

### Examples:
- Update record in database and send it to the printer
```
$db->Update(record)
record->Print()
```

### Why is communicational cohesion bad?
- Still lack of reusability
---

4- **Procedural cohesion**: is when parts of a module are grouped because they always follow a certain sequence of execution (e.g., a function which checks file permissions and then opens the file).

![procedural cohesion](/posts/images/cohesion/procedural_cohesion.jpg "procedural cohesion")

![procedural cohesion](/posts/images/cohesion/procedural_cohesion.png "procedural cohesion")

### Examples:
- Update record in database and send it to the printer
```
$userInput->All()
$validator->Validate($userInput)
$db->Store()
```
### Why is procedural cohesion bad?
- Functions are still weakly connected.
- The class is unlikely to be reusable.
---
5- **Temporal cohesion**: is when parts of a module are grouped to performs **a series of actions** related in **time** (e.g., a function which is called after catching an exception which closes open files, creates an error log, and notifies the user).

![Temporal cohesion](https://media.giphy.com/media/jWexOOlYe241y/giphy.gif "Temporal cohesion")



### Why is procedural cohesion bad?
- Functions of this class are weakly related to each other but strongly related in time.
- Not reusable.
---
6- **Logical cohesion**: is when parts of a module are grouped because they are logically categorized to do the same thing even though they are different by nature (e.g., grouping all mouse and keyboard input handling routines).

### Why is logical cohesion bad?
- The interface is difficult to understand.
- Difficult to reusable.
---

7- **Coincidental cohesion (worst)**: is when parts of a module are grouped arbitrarily; the only relationship between the parts is that they have been grouped together (e.g., a “Utilities” class).

![Low cohesion](/posts/images/cohesion/coincidental_cohesion.jpg "Low cohesion")

### How to fix the coincidental cohesion?
- Break into seperated classes each performing one task.
---

<!-- this part will change it's place with the code mess detector -->

### Low cohesion insight detector:
- Case 1: Your object has more than one responsibility.
- Case 2: Your object has methods are not related to the class at all.
- Case 3: Utility Class.
- Case 4: Hidden objects and subclasses.

## Footnotes
- [Cohesion in computer science](https://en.wikipedia.org/wiki/Cohesion_(computer_science))



<!-- part introduction -->
<!-- part one -->
<!-- 

[] 00. introduction
[] 01. Objective
[] 02. what is the bad side as side effects?
[] 03. what is the benifit -> it is the objective
[] 04. what is the benifit -> it is the objective

what is cohesion and it's types also the coupling
and how to do the best
-- coupling => focus on complixty between the objects
software guid design series
 -->
