## Objective
- Prevent known errors
- Prevent introduction of bugs
- High test coverage but can't cover everything
- Happy Testing- Test positive scenarios where you go through clean
- Fail Testing- Test bad scenarios which lead to failure

## Levels (High->Low)
**Manual**
1. Acceptance: How users interact with the program as is
2. System: How the system can function running the program works

**Automatic**
3. GUI Testing: Tests how the visuals are working
4. API Testing: Testing how the application is interfaced with the API
5. Integration Testing: Tests how something integrates with another application
6. Unit Test: Tests the function of something singularly
7. Code Review: Code reviewed by someone with experience

## Characteristics
Here are the characteristics testing should check for:
- Functionality: What the program needs to
- Usability: UX, how usable the program is to users and those who have disabilities
- Security/Penetration Testing: How secure the program is and if there are exploits
- Performance/Efficiency: How it can deal with loads and how fast requests can be dealt with
- Portability: How much the software can be used on different systems or applications
- Reliability: How robust the program is and likely to stay up

## Types of Tests
- Ad-hoc: Test on the demand as required
- Test Suite: A set of tests run at the same time
- Code Coverage: How much of the code is tested with a test

## Good Practices
- Edge Cases: Data which are not expected
- Multiple calls: How the function deals under a large load and synchronous calls
- Invalid inputs of empty or negative data
- Positive Testing
- Failure Testing

## What could go wrong
- Time outs: The program does not respond in time or at all
- Broken connection: Lost connection to an API or database
- Downtime: An application is unavailable
- Disaster Recovery: If the physical servers at the data centre goes down or breaks

## Unit Cases
- Individual Functionality
- Specific Call: Testing one set of parameters passed
- Testing one thing: Test one scenario
- Inputs & Outputs: Test parameters in and return value out

## Unit Testing Framework Keywords
### Assert
- assertTrue
- assertFalse
- assertEqual
- assertSame
- assertNotSame
- assertNull
- assertNotNull
- Exception

## Continuous Integration
- Runs tests on pushes
- Quick to hunt down issues
### Quality Assurance
- Automate the build
- Make your build self-testing
- Test in an environment that is a clone of production
- Keep the build fast