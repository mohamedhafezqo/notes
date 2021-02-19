---
title: "Cohesion In Object Oriented Design"
date: 2019-10-12T00:00:06+02:00
description: "Cohesion in software design is the degree to which the elements of a certain class belong together."
draft: false
tags: [Software Engineering]
---

Our main topic for this series is **how to write good software** with this quote
> Good software is highly cohesive and loosely coupled (Separation Of Concern).


## What is the benefit from writing a good software?

Writing **maintainable, testable and readable** code helps increase productivity for us as developers. Having highly maintainable code makes it easier to design new features and write code. Modular, component-based, and layered code increase productivity and reduce risk and cost when making changes.

## What is Cohesion?
In software design, it is the degree to which the elements of a certain class belong together.

## What is Cohesion types?
1. **Functional cohesion (best)**: This is high cohesion and that means the class should be self-contained and with a single purpose. In other words the class should do one thing and one thing very well. High cohesion is closely related to [Single responsibility principle](https://en.wikipedia.org/wiki/Single_responsibility_principle).

![High cohesion](/posts/images/cohesion/functional_cohesion_high_cohesion.jpg "High cohesion (best)")

* The elements within the object are directly related to the functionality the object is meant to provide. By keeping high cohesion within our code, we end up trying DRY code and reduce duplication of knowledge in our object. We can easily design, write, and test our code since all the code for our object is located together and works together.

* High cohesion gives us better designed code that is easier to maintain.

* We cannot always make it perfect, but we can at least strive for it.

* The point is, while building classes the lesser the elements are, the greater the possibility for reusing them in all the methods.

### Examples:
- Swiss watch: Each gear/piece is SOLID and designed to do one thing.
- Your smart phone: You can use one app while installing, updating, and/or uninstalling another! That each app is self-contained is highly cohesive.

### The benefits of high cohesion are:

- **Readability** : (closely) related functions are contained in a single object.
- **Maintainability** : debugging tends to be contained in a single object.
- **Reusability** : classes that have less elements and concentrated functionalities are not polluted with useless functions.

---

2. **Sequential cohesion**: is when parts of a class are grouped because the output from one part is the input to another part like an assembly line (e.g., a function which reads data from a file and processes the data).

![High cohesion](/posts/images/cohesion/sequential_cohesion.jpg "High cohesion (best)")

* Is this case, would there be value in "cutting"  along the dotted line ? not necessarily... Can you imagine calling "predict target" without having a call to "calculate trajectory" immediately prior to that; to acquire the information needed by the "predict" task?  the second task needs the first.

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
- Still lacks reusability
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
5- **Temporal cohesion**: is when parts of a module are grouped to perform **a series of actions** related in **time** (e.g., a function which is called after catching an exception which closes open files, creates an error log, and notifies the user).

![Temporal cohesion](https://media.giphy.com/media/jWexOOlYe241y/giphy.gif "Temporal cohesion")



### Why is procedural cohesion bad?
- Functions of this class are weakly related to each other but strongly related in time.
- Not reusable.
---
6- **Logical cohesion**: is when parts of a module are grouped because they are logically categorized to do the same thing even though they are different by nature (e.g., grouping all mouse and keyboard input handling routines).

### Why is logical cohesion bad?
- The interface is difficult to understand.
- Difficult to reuse.
---

7- **Coincidental cohesion (worst)**: is when parts of a module are grouped arbitrarily; the only relationship between each part is that they have been grouped together (e.g., a “Utilities” class).

![Low cohesion](/posts/images/cohesion/coincidental_cohesion.jpg "Low cohesion")

### How to fix the coincidental cohesion?
- Break arbitrarily grouped parts into separated classes; each of which perform one task.
---

### Recap
![flowchart for cohesion](/posts/images/cohesion/cohesion-in-software-as-a-flowchart-on-mohamedhafez-me.png "flowchart for cohesion")

![good and bad cohesion](https://upload.wikimedia.org/wikipedia/commons/b/bc/Good%2C_bad_apps.png
 "good and bad cohesion")


<!-- this part will change it's place with the code mess detector -->

### Low cohesion insight detector:
- Case 1: Your object has more than one responsibility.
- Case 2: Your object has methods that are not related to the class at all.
- Case 3: Utility Class.
- Case 4: Hidden objects and subclasses.

## Footnotes
- [Cohesion in computer science](https://en.wikipedia.org/wiki/Cohesion_(computer_science))

- Thanks [@hedayasamy](https://github.com/hedayasamy) for your review.


<!-- part introduction -->
<!-- part one -->
<!-- 

[] 00. introduction
[] 01. Objective
[] 02. what is the bad side as side effects?
[] 03. what is the benifit -> it is the objective

what is cohesion and it's types also the coupling
and how to do the best
-- coupling => focus on complixty between the objects
software guid design series
 -->
