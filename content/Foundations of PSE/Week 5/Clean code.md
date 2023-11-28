## Reasons
- Easier to debug and understand
- Easier for onboarding
- Avoids duplications as everything is concise
- Easier to follow
## Cases
- snake_case: used in python
- PascalCase: used for class name in OOP languages
- camelCase: used for variable names and methods
- UPPERCASE: used for constants
- lowercase: used for yml paths and packages (com.example.package.code)
## Naming conventions
- Class: nouns
- Packages: separated by `.`
- Methods: present tense action i.e. `getData`, `killPlayer`, `eatApple`
- Boolean: state as a fact i.e. `isAlive`, `hasEaten`
- Integer: be completely explicit i.e. `appAge`, `appUptime`
- String: be completely explicit i.e. `firstName` rather than `name`
## Method and Variable Scope
- Public: Can be seen anywhere
- Private: Can only be seen in it's class
- Protected: Can be seen by itself and subclasses
- Default (no Keyword): Can be seen by everything in it's package
- Local: see [[Scope]]
- Global: see [[Scope]]
- Constant/Final: Value cannot be changed after assignment
## Memory
People can remember 5 this on average with a high of 7
## Method - Best Practices
- Do one thing i.e. `getData` & `processData` rather than `getDataAndProcess`
- Descriptive name with what it does
- Keep variable count low
- Keep method calls low
- If either are high consider splitting up the method
## Packages - Best Practices
(Packages can be understood as folders)
- Group your classes together
- Make something easy to find
- Class name should be useful and concise
## Magic numbers
- Don't use hardcoded numbers (hard coded numbers are magic numbers)
- Use `static final` variables or `enums` so it its more readable i.e. for blackjack instead of hardcoding 21 set a variable of `winningScore` to it.
## Domain Names
- Utilise words as used by your users
- Ensure no confusion
## SOLID
### Single Responsibility Principle (SRP)
A class should only have 1 responsibility.
If changes are done to this it should only break 1 function.
### Open-Closed Principle (OCP)
A class should welcome extension but not want modification.
### Liskov Substitution Principle (LSP)
A subclass should not lose the functionality of it's parent class so whatever can be run with the parent can be used on the subclass
### Interface Segregation Principle (ISP)
An interface should only include what is required by the client
### Dependency Inversion Principle (DIP)
When building code we should focus on the interfaces/high-level parts 
## DRY
This prevents more lines of code.
Makes debugging easier as you only need to check one place
## Touch it once
Assume this is the last time you will be touching what you are working on so do not leave things to return to
## Commits
- Small commits
- Rollback
- Code reviews
## Static Analysis
- Lint - Analyses that code follows the style and has no vulnerabilities
- Space or Tabs
- Case to use in program
- Comments
- Unit test coverage