## Single Person Development
When a single person develops a codebase or area of code all by themselves from start to finish.
### Positives
- Well versed in the area
- Less people to go through for changes 
### Negatives
- If they leave nobody else knows how to do it
- If they are sick it will take awhile for someone to take it on
- Nobody checking how maintainable it is
- Nobody checking over it for assumptions
## Code Review
Developers make a change to the code, other people will check these changes and will provide feedback of the changes and possibly accept the PR.

**What is checked:**
- Readability
- Mistakes and vulnerabilities
- Prevent duplications
- Shared updates
- Ownership of changes

**What could be negative:**
- Takes time to do
- Animosity
- Can cause a blame culture
- Can break team moral
## Pair Programming
### Method 1
1 Driver, 1 Observer
Driver - makes the code changes
Observer - watches for mistakes and discusses
Frequent swapping of roles

### Method 2
1 Driver, 1 Navigator
Driver - makes the code changes
Navigator - directs the driver
## Promiscuous Pairing
1 Driver, Multiple Observers
Observers observe individually
Good for getting to know your team
End to end development with different professionals
## Mob Programming
1 Driver, Multiple observers
Driver - writes the code
Observers - discuss
Knowledge sharing/learning environment
## Test Driven Development
1. Write test
2. Test fails
3. Write code (Write the bare minimum code to pass the test)
4. Test passed
5. Refactor the code (Make code sleeker and remove duplicates)
## Pair Developer and Tester
- Pair look at and discuss a solution to an issue
- Developer will create the code to solve the solution
- Tester will write tests that might find edge cases in the developers code
- Both tests and development are done at the same time
- Independence of tester so that biases or assumptions are not made when the test is written