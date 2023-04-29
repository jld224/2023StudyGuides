# SE Study Guide:

## Process Models: 
#### A process model is a set of steps and guidelines to be followed for the development of an application. The most common process models are the Waterfall model and the Agile model. The Waterfall model follows a sequential process, with each phase coming after the other, from requirements analysis to design to implementation to testing and maintenance. The Agile model emphasizes continuous development, with the software starting from the basic design and going through a cycle of iterations until it is complete. Requirements volatility is an important factor to consider when deciding which process model to use.

#### Waterfall: Not good, Heavyweight passes with a full plan approach. Must be detailed beyond the scope of the project. OG system, orignally taught in alot of places
#### Agile: Lightweight passes, Iterative and Evolutionary with multiple passes. Individuals are more important than processes and tools, working software is a must, customer collaboration is more important than the contract, focus on responding to changes. 
#### eXtremeProgramming: Pure Agile, extreme good practices. Refactoring, Pair Programming, Collective Ownership, Coding Standards, Contiguous Integration, 40-hour work week.
#### RUP: Between Document driven and agile, very formal, invented by IBM. Iterative, Modeling and UML, Quality of process (Lots of testing), Use Case Driven.


## Software Evolution: 
#### Software evolution is the process by which software changes and gets improved over time. It can take the form of greenfield development, which is the creation of a new software system from scratch, or brownfield development, which is the modification of an existing system. Main conclusions of Lehman's Laws are that systems should be kept simple and understandable, that systems should be designed with change in mind, and that incremental changes can be more successful than complete overhauls.

#### Software Evolution = Software Development + Software Maintenance
#### Brownfield (Starting from legacy project), Greenfield (Brand new program) types of development
#### Maintenance: Corrective (fix bugs), Adaptive (Change to fit enviroment), Perfective (Improve Performance), Preventitive (Detect and correct small problems before they get worse).
#### Lehman's Laws:
1. Continuing Change
2. Increasing Complexity
3. Self Regulation
4. Conservation of Organisational Stability
5. Conservation of Familiarity
6. Continuing Growth
7. Declining Quality
8. Feedback System
#### Software must change over time. Changes cause complexity. Complexity increases the cost of change—resources allocated to reduce complexity take away from features. Software projects in an organization tend towards the same quality, bug rate, etc. Over time, the rate of development for each iteration doesn't vary much. Tend to meet the same number of goals with each iteration. Must implement features that were previously not considered necessary. Without changes, the software appears to decrease in quality.


## Refactoring: 
#### Refactoring is the process of making simple, structural changes to code to make it easier to maintain and modify. It involves breaking down a code base into manageable chunks, making sure that it follows consistent coding styles, and ensuring that variable and function names are meaningful and easy to understand. The goal of refactoring is to reduce complexity and improve readability.

#### Levels of changes: High Level (add features), Intermediate (Change design), Low (Change individual statements) 
#### Fowler: Refactoring in such away that does not alter the external behavior
#### Why? Design preservastion, Comprehension, Debugging, Faster Programming
#### When? Adding functionalities, comprehending new program, debugging, code review


## Code Smells: 
#### Code smells are indicators that code is not up to quality standards and needs to be refactored. Common code smells include long method names, long parameters, duplicate code, and improper use of comments. They can often be identified by using static analysis tools, and can be addressed by refactoring the code.

#### Categories:
- Bloaters: Long method, large class, primitive obsession, long param list
- Object-Orientation Abusers: Switch statements, Temp Field, Refused Bequest, Alternative class with different interfaces
- Change Preventers: Divergent Changes, Shotgun Surgery (lots of little changes at the same time), Parallel Inheritance Hierachies 
- Dispensables: Lazy class, Data class, duplicate code, dead code, speculative generality (Over generalized)
- Couplers: Feature Envy, Inappropriate Intimacy, Message Chains, Middle Man


## TDD: 
#### Test-Driven Development (TDD) is a software development methodology in which unit tests are written before the code is written. This helps to ensure that the code is written to fulfill its purpose and helps to drive the development process. Principles of TDD include test-first development, red-green-refactor cycle, and continuous integration. The process involves writing a test that fails, writing the code to make the test pass, and then refactoring the code to make it better.

#### No Notes, write the tests, make the tests work with the code you write


## Git Workflow: 
#### Git is a version control system used to keep track of different versions of code. It uses a workflow that involves forks, branches, and pull requests. A fork is a copy of the codebase, a branch is a way to work on different versions of the same codebase, and a pull request is a way to merge different versions of a codebase. Understanding the main Git commands is important in order to effectively use it. GitHub issues provide a way to create and discuss tasks related to the development of the codebase.

#### The most commonly used Git commands are as follows:
- git clone URL: Clone an existing repository from a remote server github.com.
- git status: Display the status of your working directory, including changes, staged files, and the current branch
- git branch: List all branches in your local repository. You can create a new branch using git branch [branch-name] or view all branches, including remote ones, with git branch --all 
- git checkout [branch-name]: Switch to the specified branch and update the working directory
- git add [file]: Stage a file for commit, preparing it for versioning
- git commit -m "descriptive message": Record the staged changes permanently in version history
- git pull: Update the current local working branch with all new commits from the corresponding remote branch on GitHub. This command combines git fetch and git merge 
- git push: Push your local changes to the remote repository. If pushing a new branch, use git push -u origin [branch-name] to create a remote branch with the same name and establish a tracking relationship 
- git remote -v: Show the associated remote repositories and their stored names, like "origin" 
- git tag [tag-name]: Create a lightweight tag
- git tag: list tags 
#### Forks: A fork is a copy of a repository that allows you to make changes without affecting the original project. It is useful when you want to contribute to a project but don't have write access to the main repository
#### Branches: Branches allow developers to work on different features or fixes simultaneously, isolating changes in a safe environment. This enables developers to commit code that might still need improvement and share it with others for feedback or testing
#### Pull Requests: A pull request is a comparison of two branches, typically the main branch and a feature branch. Pull requests enable collaboration by allowing integrated tests to run automatically and peers to give detailed code reviews. To open a pull request, push your branch to the remote repository and create a new pull request if one doesn't already exist. Once the pull request is open, you can make additional changes by committing to the same branch and pushing the changes to the remote repository
#### GitHub Issues: GitHub Issues is a feature that allows you to track bugs, enhancements, and other tasks related to a project. Issues can be assigned to specific team members, given labels for easy filtering, and linked to pull requests or commits that resolve them. This helps teams prioritize work and collaborate more effectively

 
## Software Lifespan Models: 
Software Lifespan Models are frameworks used to describe the lifespan of a software system. They describe the stages of a software system's development and provide a way of looking at a system from different points of view, including time, money (income and expenditures), and career.

#### Lifespan makes more sense than lifecycle, there are no cycles like that in software
1. Initial Development: fundamental decisions being made, technologies, architecture, program domain knowledge
2. Evolution: Adapt application to the user and operating environments, add new features, correct mistakes made in step 1, growth in size
3. Servicing: No longer evolving, just stabilizes or decays, changes limited to patches, no need for SE's
4. Phaseout: No more servicing, the system may be in production
5. Close Down: Software disconnected from users, "Exit strategy" needed, what to do with the data
#### Think about it from the perspectives of Time, Money, and Careers separately


## Software Change: 
Software change describes the process of making changes to a software system. It includes identifying the concept location to change, analyzing the impact of the proposed change, and categorizing the change into one of the maintenance categories.

**Types of changes (from Schach'03)**
- Perfective (39.0%): Focuses on enhancing the software features and performance to meet user requirements and expectations
- Adaptive (2.2%): Deals with updating the software to adapt to changes in its environment, such as new hardware, operating systems, or external dependencies
- Corrective(56.7%): Focuses on fixing errors and faults in the software, which can affect its design, logic, or code
- Other(Preventative)(2.4%): Aims to reduce the risk of software deterioration over time, making it more stable, understandable, and maintainable

**Types of functionalities**
- Incremental: Adding new features
- Contraction: Removing obsolete functionality
- Replacement: Replacing existing functionality
- Refactoring: Changing structure of software without changing the behavior

**Impact Levels**
- Local: Affects only small, immediate part of code, i.e., individual method, class, or small namespace/package
- Significant: Affects more than one part of the code or very scattered parts of the code
- Massive: Changes the entire system

**Impact Analysis** 
- Determine strategy and impact of change
- Change has not occurred yet
- Typically done at a class/file level
- impact set classes identified in concept location
- Class dependencies are analyzed, and impacted classes are added to the impact set

## Scrum: 
Scrum is an Agile software development methodology that involves breaking down the development process into small, manageable steps. It is based on the principles of collaboration, self-organization, and accountability. The fundamental steps of Scrum are the sprint, standup meeting, sprint review, and sprint retrospective. The terminology used in Scrum includes user stories, burn-down charts, product backlog, and velocity.

### Fundamental Steps
- Sprint planning: This event initiates the sprint and helps outline what can be delivered and how
- Daily Scrum meetings: Scrum teams meet daily to discuss ongoing tasks, roadblocks, and any other factors that may affect the development team
- Sprint review: At the end of each sprint, the team comes together to review the work completed, present it to stakeholders, and gather feedback
- Sprint retrospective: This recurring meeting serves as an opportunity for the team to reflect on the previous sprint, identify areas for improvement, and streamline processes for the next one

### Terminology
- Scrum Master: The person responsible for facilitating the Scrum process, removing obstacles, and ensuring the team's efficient operation
- Sprint: A time-boxed period, typically 2-4 weeks, during which a specific set of tasks are completed
- Product Backlog: A prioritized list of features, enhancements, and bug fixes required for the product
- Sprint Backlog: A list of tasks selected from the Product Backlog to be completed during the current sprint
- Increment: The sum of all completed Product Backlog items during a sprint, which together form a potentially releasable product

### Time Limits
- Sprint: Sprints typically last 2-4 weeks
- Daily Scrum: Daily Scrum meetings should be time-boxed to 15 minutes
- Sprint Planning: This event should be time-boxed to a maximum of 8 hours for a one-month sprint, with shorter sprints having proportionally shorter planning sessions
- Sprint Review: The Sprint Review should be time-boxed to a maximum of 4 hours for a one-month sprint, with shorter sprints having proportionally shorter reviews
- Sprint Retrospective: This meeting should be time-boxed to a maximum of 3 hours for a one-month sprint, with shorter sprints having proportionally shorter retrospectives


## Use Case and Use Case Diagram: 
A use case is a document that describes the interaction between a user and a system in order to accomplish a specific goal. It is typically described in a narrative format and includes the goal, the actor, and the steps that need to be taken to reach the goal. A use case diagram is a visual representation of the use case that helps to identify the actors and the steps that need to be taken in order to complete a task. User stories are more specific than use cases, and help to provide a more detailed description of the requirements of the system.

#### Actors: External entities, Users, other systems
#### Use Case: Has descriptive name, Describes what not how, captures some user-visible functionality


## SE Code of Ethics: 
The Software Engineering Code of Ethics is a set of principles set out by the IEEE to guide software engineers in their professional practice. It includes categories such as professional responsibility, public interest, product quality and safety, and loyalty.

1. PUBLIC: Software engineers shall act consistently with the public interest.
2. CLIENT AND EMPLOYER: Software engineers shall act in a manner that is in the best interests of their client and employer consistent with the public interest
3. PRODUCT: Software engineers shall ensure that their products and related modifications meet the highest professional standards possible.
4. JUDGEMENT: Software engineers shall maintain integrity and independence in their professional judgment.
5. MANAGEMENT: Software engineering managers and leaders shall subscribe to and promote an ethical approach to the management of software development and maintenance.
6. PROFESSION: Software engineers shall advance the integrity and reputation of the profession consistent with the public interest.
7. COLLEAGUES: Software engineers shall be fair to and supportive of their colleagues.
8. SELF: Software engineers shall participate in lifelong learning regarding the practice of their profession and shall promote an ethical approach to the practice of the profession.