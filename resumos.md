# Lecture 2 
## Goals
- Describe important agile development practices
- Apply the Scrum approach to agile project management
- Explain the stages of testing and the importance of automated testing
- Explain what continuous integration is

## Plan-driven development
- Based on controlled and rigorous software development processes
    - Detailed project planning, 
    - Requirements specification and analysis 
    - System modelling

- Significant overheads and documentation
- Does not support rapid development and delivery of software
- Another approach for software engineering (contrasts with agile methods)

## Agile Software Engineering
Focus:
- Rapid delivery of software
- Responding to changing product specifications
- Minimizing development overheads


## Agile Methods
- Feature-oriented
- Incremental development and delivery


### Principles
- Customer involvement
- Embrace change
- Incremental delivery
- Maintain simplicity
- People, not process

### Techniques
Extreme Programming
: Focused on new development techniques geared to rapid, incremental software development, change and delivery

- Incremental planning/ user stories
Template: As a \<type of user>, I want \<some goal> so that \<some reason>
Acceptance criteria can be explicitly defined for user stories
- Small releases: incrementally deliver valuable functionality
- Test-driven development: write tests first to ensure code reliability
- Continuous integration: integrate completed work and run tests automatically to ensure successful integration
- Refactoring: continuously improve code quality

(check table in slide 16)

### Project Management
Scrum
: Agile method that provides a framework for agile project organization and planning.

#### Key Roles
- Product Owner: ensures that development team is focused on product being built rather than less relevant technical issues
- ScrumMaster: guides team in effective use of Scrum method; coach for the team; authority within the team on how Scrum is used

#### Key Terms
- Development team
- Potentially shippable product increment
- Product backlog
- Product owner
- Scrum
- ScrumMaster
- Sprint
- Velocity 
(check table in slides)

#### Sprint Activities  
- Sprint planning
- Sprint execution
- Sprint reviewing

#### Sprint Planning
- Establish an agreed sprint goal
- Decide items from product backlog that should be implemented
- Create sprint backlog

Ideal team size: 5-8 people

#### Sprint Review
At the end of each sprint, there is a review meeting. Goal:
- Review whether or not the sprint's goal was met
- Set out problems/issues that arose during the sprint
- Process review: reflect on work and Scrum usage and how to improve

## Agile Activities
- Test automation
- Continuous integration

### Software testing goals
- Demonstrates to the developer that the software meets its requirements
- Discovers software deviations from specifications and incorrect/undesirable behaviour

### Validation and Defect Testing
Validation testing
: Demonstrates that the software meets its requirements.
A successful test shows that the software behaves as expected.

Defect testing
: Discovers software deviations from its specifications and incorrect or undesirable behaviour.
A successful test makes the system perform incorrectly.

Verification 
: Are we building the product right?

Validation
: Are we building the right product?

### Inspections and Testing
- Inspections: static verification
Can be applied to all descriptions (humans are good at reading descriptions)

- Testing: dynamic verification
Runtime behaviour of the system (computers are good at executing descriptions)

Complementary techniques, both should be used during V&V process

## Continuous Integration


# Lecture 3
## Goals
- Describe white-box and black-box testing strategies
- Apply partyition testing to create test cases
- Describe the concepts of unit testing and testing doubles
- Explain the importance of reviews and inspections


## Stages of Testing
- Development testing (developers)
System is tested during development to discover bugs and defects
- Release testing (QA engineers)
Separate testing team tests a complete version of the system before it is released
- User testing (Users)
Users (or potential) test system in their own environment

### Development Testing
Includes all testing activities carried out by the team developing the system.
- Unit testing
- Component testing
- System testing

### Testing Strategies
Black box testing
: Testing against a specification.
Tests are driven by a description that was actually used to produce the software artefact.

White box testing
: Testing against an implementation.
Tests are driven by the artefact description itself.

### Partition Testing
Identify non-overlapping groups of inputs that are expected to trigger similar behaviour.

### Unit Testing
Process of testing individual components in isolation.
Units:
- Individual functions/methods
- Classes
- Composite components with defined interfaces

Goal: increase confidence in individual units before start testing interactions between multiple units/components.

#### Automated Testing
Tests are run and checked without manual intervention. 
Uses automation frameworks (Spock, JUnit)
Components:
- Setup part
- Call part
- Assertion part

#### Test Doubles
Any kind of pretend object used in place of a real object for testing purposes (dummies, fake objects, stubs, spies, mocks)
Advantages:
- Isolate units
- Reduce dependencies between teams
- Reduce overheads of testing setup
- Simulate infrequent or difficult to generate test cases

#### Reviews and Inspections
#### Static Analysis

# Lecture 4
## Goals
- Explain the concept of code coverage
- Apply different code coverage criteria to design testing plans
- Explain what is object testing and component testing
- Describe different approaches to component testing

### Testing Strategies
- Partition testing
- Guideline-based testing

### Code Coverage
Percentage measure of the degree to which the source code of a program is executed when a particular test suite runs.
White-box testing technique.
Criteria:
- Statement coverage: each statement is executed at least once
- Branch coverage: every condition is evaluated to true and false
- Condition coverage: each boolean sub-expression of the condition is evaluated to true and false
- Path coverage: every independent path is executed. Also known as structured basis testing.

Independent path
: traverses at least one new edge in the flow graph

Number of independent paths = number of decisions + 1 (cyclomatic complexity)

### Object Testing
Unit testing: test methods in isolation
Object testing: test sequences of methods

Important to distinguish between non-modal and modal classes (object testing focuses on modal classes)

### Component testing
Test the interaction between interfaces of different components and classes.
Focus: find failures that result from interactions between units.
Goal: showing that the component interface behaves according to its specification.

#### Interface Errors
- Interface misuse
- Interface misunderstanding
- Timing errors

#### Approaches
- Big bang integration (testing components all together)
- Incrementally (bottom-up or top-down)

# Lecture 5
## Goals
- Describe the Refactoring Process
- Describe refactoring techniques and guidelines
- Explain pros and cons of test-driven development
- List different types of code reuse
- Explain the principle of Inversion of Control and the difference between a library and a framework

## Refactoring Process
Add functionality -> Test -> Change structure -> Test -> Repeat

- TDD Refactoring
- Litter-Pickup Refactoring
- Comprehension Refactoring
- Preparatory Refactoring (make the change easy, then make the easy change)
- Planned Refactoring
- Long-term Refactoring

## Workflows of Refactoring
Two hats metaphor:
- Refactoring: every change you make is a small behavior-preserving change. You only refactor with green tests, and any test failing indicates a mistake. By stringing together a series of small changes like this you can move more quickly and with less risk because you shouldn't get trapped in debugging.
- Adding Function: any other change to the code is adding function. You will add new tests and break existing tests. You aren't confined to behavior-preserving changes (but it's wise to keep changes small and return to green tests swiftly).

You may switch between hats frequently, but **you can only wear one hat at a time**.

## Refactoring Techniques
- Extract Method
- Move Method
- Reduce dependencies
- Have smaller and highly cohesive methods
- Separate presentation from domain
- Follow the high cohesion quality
- Replace conditional with polymorphism

## Test-Driven Development
Approach to program development in which you inter-leave testing and code development.
Tests are written before code - passing tests is the critical driver of development.
Incremental code development, along with a test for that increment.

### Benefits
- Code coverage
- Regression testing
- Simplified debugging
- System documentation

Regression Testing
: Testing the system to check that changes ahve not broken previously working code.

## Code Reuse
- Libraries (reuses code)
We have control -> invoke library, regain control
- Application frameworks (reuses design)
"Inversion of control" – "Don’t call us, we’ll call you"
We invoke framework -> framework gains control and invokes our code
- Code generators (generates code)
- Aspect-oriented development (generates code; code weaving. e.g.: @Transactional(isolation = Isolation.SERIALIZABLE))
- Model-driven engineering (generates code; different languages)
- Product-lines (common modules and variation modules)
- Services (shares services)

# Lecture 7
## Goals
- Describe qualities of good design
- Analyze specific designs in terms of Cohesion and Coupling
- Describe different types of interfaces
- Describe the SOLID design principles
- Describe the Law of Demeter


## Design as Structure
Module: design entity which has an interface
A class is a module in object-orientation.
Why is it difficult to change the code?
- Cost of change (100 lines of code in a class vs 1 line of code in 100 different classes)
- Propagation of change
- Locality of change

## Software Design
Goal: simplicity
- Main quality: modifiability (how easy it is to change the code).
Can be measured in terms of propgation and locality of changes

Principles that promote locality of changes: **High cohesion and low coupling**

## Cohesion and coupling
- Qualities of a good design are:

High cohesion
: Single responsibility within a module
Increases locality of change

Low coupling
: Reduces dependencies between modules
Reduces change propagation

Coupling is asymmetric.

## Design patterns
### Command
Encapsulate a request as an object, thereby letting you parameterize clients with 
different request, queue or log requests, and support undoable operations.

Coupling:
- Invoker is independent of the particular command
- Client knows the particular command
- Easy to extend with new types of command

Cohesion:
- Concrete commands contain all operations associated with the management of the operation

### Template
Defines the program skeleton of an algorithm in an operation, deferring some steps to subclasses.
Lets one redefine certain steps of an algorithm without changing the algorithm's structure.

Coupling:
- Strong coupling between subclasses and superclass because they must follow the algorithm

Cohesion:
- If the algorithm's structure needs to be changed, it is only necessary to change in superclass: superclass is cohesive
- Subclasses are cohesive in the parts of the algorithm

### Composite
Describes a group of objects that are treated the same way as a single instance of the same type of object.
Intent is to compose objects into tree strcutures to represent part-whole hierarchies.
Implementing composite pattern lets clients treat individual objects and compositions uniformly.

Coupling:
- Client depends on interface common to all members
- Members use the same interface when interacting eac other
- Easy to extend with new types of members

Cohesion:
- Each member contains the responsibilities associated with its function

### State
Encapsulates varying behaviour for the same object, based on its internal state.
Allows an object to alter its behavior at runtime without resorting to conditional statements.
Improves maintainability.

Coupling:
- Context is decoupled from state, where state encapsulates its implementation.

Cohesion:
- Concrete state is cohesive in terms of its set of operations.
- Operation is split between the different states.

## Interfaces and Abstractions
- Different types of abstractions enable different levels of coupling
- Good interface depends on good abstraction
- Good abstractions take time and experience to develop
- Good abstractions depend on the context (argument to define abstractions bottom-up)

## Design Process
Top-Down
: From requirements to design structure

Bottom-Up
: Refactoring of implemented functionality

### Top-down approach to design
- System context and interaction
- Architectural design
- Object class classification
    * Inferred from use cases
    * Domain entities
- Design models
    * Blueprints from programmers
- Interface specification
    * Programmerrs can work in parallel

## Design Principles (SOLID)

### Open-Closed Principle
Modules should be open for extension but closed for modification.
- Low coupling from clients
- High hierarchical cohesion

### Dependency Inversion Principle
High-level modules should not depend on low-level modules. 
|-> Both should depend on abstractions.
|->-> Abstractions should not depend on details.
|->->-> Details should depend on abstractions.
- Low coupling by depending on abstractions

### Interface Segregation Principle
Clients should not be forced to depend upon interfaces they do not use.
- Low coupling by depending on minimal responsabilities

### Single Responsibility Principle
A module should have only one reason to change
- High cohesion

### Liskov's Substitution Principle
Derived types must be completely substitutable for their base types.
- Low coupling because extensions preserve the abstraction

## Lei de Demeter (bem definida?)
An object should assume as little as possible about the internal workings of other modules.
- Each unit should have limited knowledge about other units
- Only closely related units should interact (only speak to your closest friends)

Specific case of loose coupling.

# Lecture 8
## Goals
- Distinguish between functional and non-functional requirements
- List and describe important qualities of requirements
- Describe the Requirements Engineering Process
- Explain what is Software Architecture
- Describe common Architectural Patterns and Application Architectures

## Requirements Engineering
Understand what needs to be solved. 
Transform the **user requirements** (solution from the user perspective) into **system requirements** (problem from the developer perspective).

Functional requirements
: What the system should do (system behaviour)

Non-functional requirements
: How the system performs and what constraints it must satisfy 

### Qualities of requirements
- Completeness: do they capture all relevant aspects?
- Consistent: different stakeholders; security vs availability
- Measurable: the system should resist attacks

[TODO completar depois, isto é muito aborrecido, ES-08-1-Requirements Engineering, slide 46 onwards]

## Software Architecture
- High level design for the stakeholders (client, end user, development team, business team).
- It should:
    * Satisfy stakeholder needs
    * Demonstrate system qualities
- **Stakeholder needs** equal the **system qualities** and include (non-functional requirements):
    - Security
    - Time to market
    - Performance
    - Maintanability
    - Availability

They may conflict - software architect defines the tradeoff among different stakeholder needs.


### Architectural Design Decisions
- Generic application architecture that can act as template
- Fundamental approach to structure the system
- How to decompose structural components into sub-components
- Best architectural organization to delivering the non-functional requirements
- Documentation of the system architecture
- Strategy to control the operation of components
- Patterns or styles that might be used
- Distribution of the system across hardware cores/processors

### Architectural Views
Different perspectives of the system architecture.
- Logical view
- Physical view
- Development view
- Process view

## Architectural Patterns (TODO falta Used when:, I forgor)
Used to restrict number of possible forms.

### Model-View-Controller
Separates an application into three interconnected components:
- Model
    * Encapsulates application state 
    * Notifies view of state changes
- View 
    * Renders model 
    * Requests model updates 
    * Sends user events to controller
- Controller: 
    * Maps user actions to model updates 
    * Selects view

Advantages: 
- Allows data to change independently of its representation and vice versa
- Supports presentation of the same data in different ways w3ith changes mande in one representation shown 

Disadvantages:
- Can involve additional code complexity when data model and interactions are simple

### Layered
Organizes the system into multiple layers, where each provides services to the layer above and uses services from the layer below. Example:
- User interface
- User interface management + authentication and authorization
- Core business logic / System utilities
- System support (OS, database...)

Advantages:
- Allows replacement of entire layers so long as the interface is maintained
- Redundant facilities an be provided in each alyer to increase dependability of the system

Disadvantages:
- Providing a clean separation between layers is often difficult; a high-level layer may have to interact directly with lower-level layers rather than through the layer immediately below it
- Can lead to performance problems 

### Repository
All data in a system is managed in a central repository, accessible to all system components. They don't interact directly, only through the repository.

Advantages:
- Components can be independent
- Changes made by one component can be propagated to all components
- All data can be managed consistently (all in one place)

Disadvantages:
- Repository is a single point of failure
- May be inefficient in organizing all communication through the repository
- Distributing the repository can be difficult

### Client-server
Functionality of the system is organized into services, each delivered from a separate server. Clients use them and access servers to make use of them.

Advantages:
- Servers can be distributed across a network
- General functionality can be available to all clients and doesn't need to be implemented by all services

Disadvantages:
- Each service is a single point of failure (susceptible to DoS attacks and server failure)
- Performance may be unpredictable (depends on network)
- Management problems if servers are owned by different organizations

### Pipe and filter TODO fazer este foda-se não me apeteceu, já faço


## Application Architectures (TODO um bocado incompleto, slides de merda)
Application architectures are architectures for a type of system; they define application independent solutions. Examples are:

- Transaction Processing Systems (transactional context)
- Information Systems
- Language Processing Systems

# Lecture 10
## Goals
- List and describe properties of Enterprise Applications
- Describe how Enterprise Applications are usually layered
- Describe the Domain Logic Patterns: Transaction Script, Domain Model, Table Module, Service Layer

## Patterns of Enterprise Applications
An enterprise application has:
- Persistent and a large amount of data
- Concurrent access
- Large number of user interfaces
- Application integration
- Complex domain logic

Structure:
Presentation logic
Services
Domain logic
Remote access + data access
Remote service + Database Transaction Manager

## Domain Logic Patterns
### Transaction Script
Organizes business logic by procedures where each procedure handles a single request from the presentation.
Most business applications can be thought of as a series of transactions, that view or change information and contain a certain amount of logic, as simple as displaying information in the database or involving many steps of validations and calculations. 
A transaction script organizes all this logic primarily as a single procedure, making calls directly to the database on a thin database wrapper. Each transaction will have its own transaction script, although common subtasks can be broken into subprocedures.

### Domain Model
An object model of the domain that incorporates both behaviour and data.
Ideal for complex business logic scenarios, where rules and behaviour describe various cases and interactions.
Creates a web of interconnected objects, where each object represents some meaningful entity within the domain.

### Table Module
A single instance that handles the business logic for all rows in a database table or view.
One of the key messages of object orientation is bundling the data with the behaviour that uses it. The traditional object-oriented approach is based on objects with identity, along the lines of Domain Model. Thus, if we have an Employee class, any instance of it corresponds to a particular employee. This scheme works well because once we have a reference to an employee, we can execute operations, follow relationships and gather data on him.

### Service Layer
Defines an application's boundary with a layer of services that establishes a set of available operations and coordinates the application's response in each operation.

# Lecture 11
## Object-Relational Behavioral Patterns
Design patterns that address the interaction between objects in an OOP environment and relational databases. They facilitate the mapping between the object-oriented domain model and the relational database schema.
### Unit of Work
Maintains a list of objects affected by a business transaction and coordinates the writing out of changes and the resolution of concurrency problems.
Necessary to keep track of:
- New objects
- Deleted object
- Updated objects (dirty)
- Read objects (clean)

#### Caller registration
- Client code explicitly informs the Unit of Work about changes to objects
- Provides control to the client but can lead to increased complexity

#### Object registration
- Domain objects autonomously register themselves with the Unit of Work
- Promotes an object-oriented design and encapsulates persistence logic

#### Unit of work controller
- A dedicated controller component manages the Unit of Work
- Centralizes management, simplifies client code, and promotes encapsulation

#### Class registration
- Registration occurs at the class level rather than individual objects
- Simplifies registration process by abstracting it at the class level

### Identity Map
Ensures that each object gets loaded only once by keeping every loaded object in a map. Looks up objects using the map when referring to them.
Loading the same object to memory twice can trigger consistency and performance problem - it is necessary to have a unique key for all objects.

### Lazy Load
An object that doesn't contain all the data you need but knows how to get it. 
By loading one object, we would load a huge number of related objects. Lazy load interrputs this loading, marks the object and if the data is needed, it is loaded when it is used. There are four varieties:
- Lazy initialization: on field access, check first if the field is null, and load it if needed
- Virtual proxy: a proxy of the object which loads the real object on demand
- Value holder: wraps the real object
- Ghost: real object in a partial state (only loads the identity)

## Data Source Architectural Patterns
### Table Data Gateway
Object that acts as a gateway to a database table. One instance handles all the rows in the table.

- Localizes all SQL code for a table in its own class
- Doesn't provide an object-oriented interface

### Row Data Gateway
An object that acts as a Gateway to a single record in a data source. There is one instance per row.

- Localizes all SQL code for a table in its own class
- Provides an object-oriented/instance interface
- Doesn't contain the domain logic

### Active Record
An object that wraps a row in a database table or view, encapsualtes the database access, and adds domain logic on that data.

- SQL Code and domain logic are in the same class
- Provides an object-oriented/instance interface
- Contains the business logic
- One-to-one mapping between object structure and database structure


### Data Mapper
A layer of mappers that moves data between objects and a database while keeping them independent of each other and the mapper itself.
 
- Separates SQL code from domain logic
- Provides an object-oriented interface
- Contains the business logic
- Allows different mappings between the object structure and the database structure

# Lecture 12
## Web Presentation Patterns
Address the organization and presentation of user interfaces in web applications.
### Model View Controller
Splits user interface interaction into three distinct roles.
- View: what the user sees
- Controller: what the user utilizes
- Model: manipulated by the controller and updated by the view

Flow:
1. User makes a request to controller
2. Controller contacts the model (abstraction layer for the database request)
3. Model returns data to controller
4. Controller delivers data to view
5. View displays data to user


### Template View
- Renders information into HTML by embedding markers in an HTML page
- What you see is what you get (WYSIWYG) description of a web page
- Support dynamic content through the use of markers
- Tradeoff to avoid turning the page too difficult to read and maintain
Example:
    * Java code inside a template?
    * Logic inside the helper?
    * Specialized tags?

### Front Controller
Controller that handles all requests for a web site
- Do not duplicate common behaviour
- Single handler object provides the common behaviour; modifiable at runtime with decorators
- Handler can be statically or dynamically decorated
- Handler and commands are part of controller - commands should choose which view to use for the response
- Simplifies the configuration of the web server (contained in handler instead of scattered through several page controllers)

## Structural Patterns

### Identity Field
Saves a database ID field in an object to maintain identity between an in-memory object and a database row.

### Foreign Key Mapping
Maps an association between objects to a foreign key reference between tables.
List updates:
- Delete and insert
- Add a back pointer
- Diff the collection

### Association Table Mapping
Saves an association as a table with foreign keys to the tables that are linked by the association.
Queries are done in two stages.

### Single Table Inheritance
Represents an inheritance hierarchy of classes as a single table that has columns for all the fields of the various classes.

### Class Table Inheritance
Represents an inheritance hierarchy of classes with one table for each class.

### Concrete Table Inheritance
Represents an inheritance hierarchy of classes with one table per concrete class in the hierarchy.

### Remain
- Dependent Mapping

- Embedded Value

- Serialized LOB

- Inheritance Mappers


## Distribution Patterns

### Remote Facade
Provides a coarse-grained facade on fine-grained objects to improve efficiency over a network.
- Great to deal with complex logic
- Inter-process calls are orders of magnitude more expensive than in-process calls
- Access and transaction control can be managed in the Remote Facade

### Data Transfer Object
Object that carries data between processes in order to reduce the number of method calls.
- Aggregates data from several objects
- Need to be serialized

# Sommerville Book

## Chapter 3 (Agile Software Development)
### Introduction
In a rapidly changing global business environment, the demand for quick software development to respond to new opportunities and competition is paramount. Plan-driven approaches struggle with this as they rely on complete, stable requirements which are unfeasible in such environments. Agile methods, such as Extreme Programming, Scrum, and DSDM, have emerged to address this need for rapid software development.

Agile methods share common characteristics:

1. Specification, design, and implementation are interleaved without detailed system specifications.
2. Development occurs in increments with end-users involved in each stage, proposing changes and new requirements.
3. Extensive tool support is used, including automated testing, configuration management, and system integration tools.

Agile methods involve small, frequent releases of the system, engaging customers for rapid feedback on changing requirements, and minimizing documentation. They view design and implementation as central activities, incorporating other tasks such as requirements elicitation and testing into these activities.

Contrastingly, plan-driven approaches delineate separate stages in the software process with outputs associated with each stage, relying on formal documentation and communication between stages.

In practice, plan-driven processes may integrate some agile programming practices, while agile methods may incorporate planned activities apart from programming and testing. Agile processes are not necessarily code-focused and may produce design documentation or system models depending on the iteration's objectives.

### 3.1 Agile methods


### 3.2 Agile development techniques

### 3.3 Agile project management

### 3.4 Scaling agile methods

## Chapter 9.3.3 (Refactoring)
Refactoring is the process of improving the structure, reducing complexity, and enhancing readability of a program without changing its external behavior. It is not limited to object-oriented development and can be applied to any development approach. Refactoring is considered as preventive maintenance to prevent degradation of program quality over time.

In agile methods, refactoring is inherent as they are based on change. Agile developers frequently refactor their programs to avoid degradation, with regression testing helping to mitigate risks. Refactoring involves identifying and addressing "bad smells" in the code, such as duplicate code, long methods, switch statements, data clumping, and speculative generality.

There are various refactoring techniques, such as Extract Method, Consolidate Conditional Expression, and Pull Up Method, which are supported by interactive development environments like Eclipse. Refactoring during program development helps reduce long-term maintenance costs.

However, if a program's structure has significantly degraded, simple code refactoring may not suffice. In such cases, design refactoring, which involves identifying and implementing relevant design patterns, may be necessary, though it can be more expensive and challenging.

## Chapter 24.3 (Reviews and Inspections)

Reviews and inspections are quality assurance activities that aim to check the quality of project deliverables, including software, documentation, and process records. These activities are conducted alongside program testing as part of software verification and validation processes.

During reviews, a group of individuals examines the software and associated documentation to identify potential problems and nonconformance with standards. The review team assesses the quality of the software or project documents, and project managers use these assessments to make planning decisions and allocate resources.

Quality reviews are based on various documents produced during the software development process, such as specifications, designs, code, test plans, and user manuals. Reviews ensure the consistency, completeness, and adherence to quality standards defined for the project.

Reviews serve not only to check conformance to standards but also to identify problems and omissions in the software or documentation. Review conclusions are formally recorded as part of the quality management process, and any issues discovered are communicated to the responsible parties for correction.

The primary purpose of reviews and inspections is to improve software quality, not to evaluate the performance of individuals in the development team. Reviews are conducted publicly to detect errors, fostering a culture of constructive engagement within the programming team.

It's important to note that quality reviews differ from management progress reviews, which focus on assessing the actual progress of a software project against planned progress. Progress reviews primarily concern whether the project will deliver useful software on time and within budget, considering external factors that may impact project requirements or viability. Despite producing high-quality software, projects may still face cancellation due to changes in business or operating environments.

### 24.3.1 Review Process

The review process consists of three main phases:

1. Pre-review activities: These preparatory activities involve review planning and preparation. Review planning includes setting up the review team, scheduling the review, and distributing the documents to be reviewed. During review preparation, team members individually read and understand the software or documents and relevant standards. They independently identify errors, omissions, and deviations from standards.

2. The review meeting: During this meeting, an author of the document or program being reviewed guides the review team through the document. The review itself should be relatively short, typically lasting no more than two hours. A designated chair leads the review, ensuring all submitted comments are considered. Another member records all review decisions and actions to be taken. After the review, the chair signs off on the record of comments and actions agreed upon.

3. Post-review activities: Following the review meeting, identified issues and problems must be addressed. Actions may involve fixing software bugs, refactoring software to meet quality standards, or rewriting documents. Sometimes, management review may be necessary to allocate additional resources for corrections. After changes are made, the review chair ensures that all review comments have been addressed. Occasionally, a follow-up review may be required to verify that all previous review comments have been adequately addressed.

Review teams typically consist of three to four principal reviewers, including an experienced designer responsible for significant technical decisions. Additional project members may be invited to contribute to the review, focusing on sections relevant to their work. Alternatively, the review team may solicit written comments from a broader spectrum of project members. The project manager's involvement in the review is optional unless issues requiring changes to the project plan are anticipated.

While traditional review processes involve face-to-face meetings, remote reviewing is becoming more common due to distributed project teams. Remote reviews can be facilitated using shared documents where team members can annotate with their comments. The review chair coordinates comments and discusses changes individually with team members, especially when face-to-face meetings are impractical.

### 24.3.2 Program Inspections

In program inspections, team members collaboratively review the source code of a program to identify bugs and defects. These inspections complement testing by allowing for the verification of incomplete system versions and other representations like UML models. During inspections, team members meticulously examine the code, searching for logical errors, anomalies, and omitted features. This process involves using checklists tailored to specific programming languages and application domains to focus the search for bugs. Research indicates that inspections are highly effective in finding defects, with detection rates surpassing those of traditional testing methods. Despite their effectiveness, some software development companies are hesitant to adopt inspections due to concerns about additional costs and uncertainties regarding potential savings in testing expenses.

| Fault class               | Inspection check                                                     |
|---------------------------|----------------------------------------------------------------------|
| Data faults               | - Are all program variables initialized before their values are used? |
|                           | - Have all constants been named?                                     |
|                           | - Should the upper bound of arrays be equal to the size of the array or Size 21? |
|                           | - If character strings are used, is a delimiter explicitly assigned? |
|                           | - Is there any possibility of buffer overflow?                       |
| Control faults            | - For each conditional statement, is the condition correct?           |
|                           | - Is each loop certain to terminate?                                 |
|                           | - Are compound statements correctly bracketed?                      |
|                           | - In case statements, are all possible cases accounted for?           |
|                           | - If a break is required after each case in case statements, has it been included? |
| Input/output faults       | - Are all input variables used?                                      |
|                           | - Are all output variables assigned a value before they are output?   |
|                           | - Can unexpected inputs cause corruption?                            |
| Interface faults          | - Do all function and method calls have the correct number of parameters? |
|                           | - Do formal and actual parameter types match?                        |
|                           | - Are the parameters in the right order?                             |
|                           | - If components access shared memory, do they have the same model of the shared memory structure? |
| Storage management faults | - If a linked structure is modified, have all links been correctly reassigned? |
|                           | - If dynamic storage is used, has space been allocated correctly?     |
|                           | - Is space explicitly de-allocated after it is no longer required?    |
| Exception management faults| - Have all possible error conditions been taken into account?         |


