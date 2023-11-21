## Requirements
Keys must be:
- Unique
- Hashable
- Immutable
## Hashing
Hashing is used to map keys to a fixed-length value which allows access to be done quicker.
### Why is it done
Computers in a basic level think in numbers, let's have 2 scenarios; a linear search and a hash
We will have a dictionary as shown: `dict = {"a": 1, "b": 2, "c": 3, "d": 4, "e": 5}`

To find value in `e` linearly it will take 5 runs through the loop
```python
def get(str):
	for key in dict:
		if key == str
			return str
	raise KeyError("Key does not exist in dict")
```

To find `e` using hashes it will take 1 run (notice how there are no loops except when a collision occurs)
```python
def get(str):
	hash = getHash(str) # We don't need to know how hashing algorithms work
	return getHashData(hash, str)

def getHashData(hash, str):
	data = getDataAtHash(hash)
	if len(data) == 1:
		return data[0]
	elif len(data) > 1
		for item in data:
			if item == str:
				return str
	else
		raise KeyError("Key does not exist in dict")
```
Linear has an O(n) complexity all the time
Hashing has O(1) best-average and O(n) at worst
## Iterating
Loop over keys:
```python
for key in dict:
	print(key)
```
Loop over keys and values
```python
for key, value in dict.items()
	print(key, value)
```
Loop over values
```python
for value in dict.values():
	print(value)
```
## Accessing
If value is inside dictionary
```python
if("value" in dict)
```
## Copies
### Shallow
Shallow copies create a new dictionary that copies values but immutable values are references and will update the old version
### Deep
Shallow copies create a new dictionary that copies values in the dictionary without any references
## Update
The update function allows you to merge dictionaries
```python
a = {"a": 1, "b": 2, "z": 3}
d = {"b": "changed", "d": "new"}
{'a': 1, 'b': 2, 'z': 3}
a.update(d)
print(a) # {'a': 1, 'b': 'changed', 'z': 3, 'd': 'new'}
```
## Delete
The delete function allows you to delete items in a dictionary
```python
del list["key"]
```
