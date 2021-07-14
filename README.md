# Bullseye Model
Bullseye Model is an approach to modeling software. The model looks at software in the shape of a bullseye target, in which the outer-most ring is the overall technical scope of the services and the inner-most ring is the specifics of code implementation in that same service.

## Goal
The of the Bullseye Model is help you avoid situations (and we've all been there) where you think something is rather simple, but find yourself trying to figure out the logic of your code during the coding process. This can end up being a colossal waste of time while you rethink things, realize things you hadn't thought about, and inevitably have to re-write a lot of your code.

Idealy, you're software has already been thought through by the time you start coding, resulting in clearer code and more reliable, scalable software.

## Leading Principles
### 1. Recognition that there is no one true way of doing something.
While the Bullseye Model does  suggest specific exercises to use when thinking through each layer, they are merely suggestions and shouldn't be considered requirements. The only thing that is a requirement is that each layer be considered and thought through. In other words, if you (or your team) want to write a five page essay describing how something will work instead of creating a diagram, have at it - just as long as it's considered and thought through.

### 2. Inclusion
It's  important that all people and team members be able to contribute. That said, it's important to remember that the degree to which you can architect and think about something is likely dependent on your experience level. As such, the Bullseye Model isn't going to teach you everything you need to know about all aspects of software development, however will help break things down in such a way that will point more junior developers in the right direction(s).

## Approach
As mentioned before, the Bullseye Model uses a bullseye target to map out the layers of software architecture. Those layers are as follows:

![Bullseye Model Target](/assets/target.png "Bullseye Model Target")

### 1. Project Scope
A well-defined explanation of the scope of the project is key in being able to effectively move forward. Why is this important, you might ask? We need to define our project scope for a number of reasons.

First, it limits the work you have to do and ensures both other people, as well as you, don't endlessly add thing to your to-do list to extent that you can't possibly keep up.

Second, it helps developers understand the task in hand, both in terms of the technical consideration, as well as what the end result needs to be.

Note: The scope here is from a technical perspective, not a business one. In other words, you may have received a project brief from your PM, but you'll still want analyze that and formulate a technical objective. This is because you may very well find that it can (and should) be broken down into multiple smaller projects from a technical perspective.

### 2. Define Packages
Perhaps more necessaary for back-end systems than front-end (though not necessarily the case), I would suggest breaking down the problem into domains, each tackling a specific piece of the puzzle while working together to achieve the overall goal.

This could manifest itself in different ways, and of course, can also be applied at different levels of abstraction. For example, you might look at a full-stack application and separate things by front-end vs. back-end. From there you could focus on the back-end and consider having a database package that facilitates DB communications and an auth package that acts as middleware to make sure requesti from the front-end are authenticated and/or authorized.

### 3. Package Scope and Context
More info coming soon

### 4. UML+ Diagrams
More info coming soon

### 5. API Definition
More info coming soon

### 6. Process Flow
More info coming soon

### 7. Data Flow
More info coming soon

## To-Do
1. Consider how this model can help developers break things down into manageable tasks (whether they keep those task in their head or use something such as Jira is up to them)