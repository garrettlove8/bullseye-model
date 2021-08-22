# Overview
Bullseye Model is an approach to modeling software. The model looks at software in the shape of a bullseye target, in which the outer-most ring is the overall technical scope of the services and the inner-most ring is the specifics of code implementation in that same service.

# Goal
The of the Bullseye Model is help you avoid situations (and we've all been there) where you think something is rather simple, but find yourself trying to figure out the logic of your code during the coding process. This can end up being a colossal waste of time while you rethink things, realize things you hadn't thought about, and inevitably have to re-write a lot of your code.

Idealy, you're software has already been thought through by the time you start coding, resulting in clearer code and more reliable, scalable software.

# Leading Principles
## 1. Recognition that there is no one true way of doing something.
While the Bullseye Model does  suggest specific exercises to use when thinking through each layer, they are merely suggestions and shouldn't be considered requirements. The only thing that is a requirement is that each layer be considered and thought through. In other words, if you (or your team) want to write a five page essay describing how something will work instead of creating a diagram, have at it - just as long as it's considered and thought through.

## 2. Inclusion
It's  important that all people and team members be able to contribute. That said, it's important to remember that the degree to which you can architect and think about something is likely dependent on your experience level. As such, the Bullseye Model isn't going to teach you everything you need to know about all aspects of software development, however will help break things down in such a way that will point more junior developers in the right direction(s).

# Approach
As mentioned before, the Bullseye Model uses a bullseye target to map out the layers of software architecture. Those layers are as follows:

![Bullseye Model Target](/assets/target.png "Bullseye Model Target")

## 1. Project Scope
A well-defined explanation of the scope of the project is key in being able to effectively move forward. Why is this important, you might ask? We need to define our project scope for a number of reasons.

First, it limits the work you have to do and ensures both other people, as well as you, don't endlessly add thing to your to-do list to extent that you can't possibly keep up.

Second, it helps developers understand the task in hand, both in terms of the technical consideration, as well as what the end result needs to be.

Note: The scope here is from a technical perspective, not a business one. In other words, you may have received a project brief from your PM, but you'll still want analyze that and formulate a technical objective. This is because you may very well find that it can (and should) be broken down into multiple smaller projects from a technical perspective.

## 2. Define Packages
Perhaps more necessaary for back-end systems than front-end (though not necessarily the case), I would suggest breaking down the problem into domains, each tackling a specific piece of the puzzle while working together to achieve the overall goal.

This could manifest itself in different ways, and of course, can also be applied at different levels of abstraction. For example, you might look at a full-stack application and separate things by front-end vs. back-end. From there you could focus on the back-end and consider having a database package that facilitates DB communications and an auth package that acts as middleware to make sure requests from the front-end are authenticated and/or authorized.

You could certainly be even more granular in how you choose to define and organize the packages in your project and I'd encourage you to do so in an effort to produce loosely-coupled code.

**Note: I think this is a good start for this section but definitely can iterate, be more descriptive, and go into more detail here**

## 3. Package Scope and Context
An argument could be made that this section should fall under the previous one, and perhaps one day it will, however for the time being, let's discuss the importance of clearly defining and articulating each package's scope and context within a project.

Similar to how we defined the project's scope at a high level back in step one, we must do the same on a package level. This will help with a number of things:
1. Enable day-one developers to agree on the boundaries in which each package should operate.
2. Help future developers understand who each package does and why it exists.
3. Help show where new features should be added (that being an existing package or the need for a new one)

All of this before any code is even written.

The piece of this puzzle is the context - that is, how does a package fit into a project? This is a pre-cursor to designing the process flow in step six.

### UML Diagrams
Consider using the following UML diagrams to help with this stage of the architecture process.

1. [Package and Model Diagrams](https://www.uml-diagrams.org/package-diagrams-overview.html)
2. [Class and Object Diagrams](https://www.uml-diagrams.org/class-diagrams-overview.html)
3. [Composit Structure Diagrams](https://www.uml-diagrams.org/composite-structure-diagrams.html#collaboration-use-diagrams)

**Note: As I read this section back over and over it feels increasingly more appropriate that it be a part of step two.**

## 4. UML Diagrams
As a general rule-of-thumb, each step should be accompanied by at least one UML diagram, which we'll go over here.

**Note:** A common complaint with UML diagrams is they can eassily become stale. While I don't have all the answer on how to prevent this, here are three things to consider:
1. Different types of diagrams become stale at different rates. A diagram that illustrates the use-cases of a project will likely not change as often as a diagram that shows how and where various interfaces are impelemented.
2. There are packages out there that will help you by automatically generating class diagrams as you update your code. For example, in Go there is [GoPlantUML](https://github.com/jfeliu007/goplantuml).
3. If you always start will the architecture part of developing software (including for subsiquent software updates) your diagrams shouldn't become too outdated because you'll always include updating them in the development process, before you even touch any code.

## 5. API Definitions
Let's talk about the APIs your software will expose (for example, RESTful endpoints), both at the public level to other software using your software, and internally, (for example, if you've broken things down into packages or classes).

While you don't need to have figure out and document every detail of your software's API implementations, you should come up with a clear understanding and starting point for how other software will interact with it. 

There will no doubt be unknowns at this point which you can't possibly design for, but more likely than not, there is **at least** one thing you do know, which you can design for. This is a great starting point and foundation, which will only make things easier as you progress through your project.

Ultimately, the API docs you create during this stage in a project will be built on as it progresses and should serve as the single source of truth for this documentation.

### API Deisgn Goals
1. Declare APIs that are consistent across all levels of your software.
2. Understand and clearly define how software and developers can interact with your software
3. Treat API documentation as a priority when it comes to developing the software (software with out documentation is borderline useless).

Remember, it's one thing to not properly document the internals of how your software is built since that will only effect other developers working on it with you. However, it's a completely different thing (way worse) to not document how software completely separate from yours can interact with your API. Software who's public 

### Approaches API Docs
To start, it's worth noting that you have your own way of documenting your software's APIs go for it - as long as you do it. What matters is that it's done and is useful, not that you follow a specific approach.

**HTTP**

Using something like the [OpenAPI specification](https://github.com/OAI/OpenAPI-Specification), you design useful and effective APIs.

You can also uses tools to generate your documentation such as [Swagger](https://swagger.io/) to auto generate a documentation UI for easy reference and discovery.

**Package**
If you are building your software in a modular fashion, with pieces broken down into components, package, or libraries, you'll want to clearly define how each of these pieces should be used.

It's important to note that if you've followed this architecture model in order, you've already done this in step two, [Define Packages](##2.-define-packages).

## 6. Process Flow
Now that we have at least one clearly defined use case, the package definitions, and some understanding of how our API(s) will be designed, we can start to think about what needs to happen with our software in order for the end-user to accomplish their business requirement(s) in a given usage scenario.

While we don't need to declare every function (we can't reassonably expect to be able to do this at this point), we can start to piece together how the flow of process execution should work when performing a given task.

### UML Diagrams
For the process flow, consider using any combination of an [Activity Diagram](https://www.uml-diagrams.org/activity-diagrams.html), [Communication Diagram](https://www.uml-diagrams.org/communication-diagrams.html), [State Machine Diagrams](https://www.uml-diagrams.org/state-machine-diagrams.html), [Sequence Diagram](https://www.uml-diagrams.org/sequence-diagrams.html), or [Interaction Overview Diagram](https://www.uml-diagrams.org/interaction-overview-diagrams.html).

## 7. Data Flow
Going down a level, once we have our process flow nailed down, we can start to think about the type(s) of data we'll need as a program moves through its processes.

```
Note: We already know the data types that will be used in each package.
```

### UML Diagrams
For the process flow, consider using any combination of an [Information Flow Diagram](https://www.uml-diagrams.org/information-flow-diagrams.html).


# To-Do
1. Consider how this model can help developers break things down into manageable tasks (whether they keep those task in their head or use something such as Jira is up to them)
2. Add a section on where to put all this additional documentation. I'm thinking some combination of added sections to a `readme`, an additional `architecture.md` file, or even `readme` files in each package.
3. Create an example architecture using the bullseye model (perhaps for one of my own projects).

- [] Add section on deployment strategy.
- [x] Add section on deployment strategy.
- [ ] Add section on deployment strategy.