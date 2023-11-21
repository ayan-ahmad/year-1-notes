## Definition
Coupling is how independently something is, can it be run as a standalone service?
The ideal scenario has low coupling.
## Coupling Types
### Content Coupling
Content coupling is when the thing you are working is heavily intertwined with the function of something else.
i.e. having a card game program heavily reliable on a card game library, any changes to the functions called in this library can break the game
### Common Coupling
Common coupling is when global data can be accessed.
Let's say we have a GameManager and PlayerManager class that both have access to the CardGame.players, this would be common coupling
### External Coupling
External coupling is when data from an external source (e.g. external file, device, etc.) is used in a program
### Control Coupling
Control coupling is when the information provided from another source controls the flow and execution of the program.
i.e. the fire alarm is pulled and is detected in the sprinkler class, the sprinkler class then opens the valves
### Stamp Coupling
Stamp coupling is when multiple methods have access to the same composite data structure
### Data Coupling
Data coupling is when data is shared through parameters from one file to another