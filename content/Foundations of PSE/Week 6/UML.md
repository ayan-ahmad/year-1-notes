## Definition
A standardized way with visuals to show various parts of software design
## Class Diagrams
- Name
- Attributes
	- Name - camelCase
	- Visibility (- Private, # Protected, + Public)
	- Type
- Operators
	- Name - camelCase
	- Visibility (- Private, # Protected, + Public)
	- Parameters (Name & Type)
	- Return type
## Relationships
|Generalisation|Type|Description|Shape|
|-----|------|------|------|
|Is a |Inheritance| `x` is a `y` means `x` is a subclass of `y`|Triangle Solid|
|Has a |Aggregation| `x` has a `y` means that the child `y` cannot live outside the context of x|Diamond Solid|
|Has a/made with |Composition| `x` made with `y`, this means that `x` would work without `y`|Diamond Empty|
https://stackoverflow.com/a/2218970


> [!warning] You will not need to be able to draw this in an exam