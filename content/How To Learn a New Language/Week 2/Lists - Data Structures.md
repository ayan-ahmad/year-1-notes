### Splicing
Generally
```python
list[start:end:jump]
```
To reverse
```python
list[::-1]
```
### Accessing
```python
list[index]
```
### Iterating
```python
for item in list:
	print(item)
```
## Length
```python
len(list)
```
## Adding values
### Appending
```python
num_list = [1,2,3] # [1,2,3]
num_list.append(4) # [1,2,3,4]
num_list.append([5,6,7]) # [1,2,3,4,[5,6,7]]
```
### + Operator
```python
num_list = [1,2,3] # [1,2,3]
num_list += 4 # TypeError
num_list += [4] # [1,2,3,4]
num_list += [5,6,7] # [1,2,3,4,5,6,7]
num_list += [[8,9,10]] # [1,2,3,4,5,6,7,[8,9,10]]
```
## Pop
```python
num_list = [1,2,3]
print(num_list.pop(0)) # 1, index as argument
print(num_list) # [2,3]
```
## Index
```python
fav_words_list = ["silly", "conveluted", "silly", "preposterous"]
fav_words_list.index("silly") # 0, this is because it only counts the first occurence
```
## Count
```python
fav_words_list = ["silly", "conveluted", "silly", "preposterous"]
fav_words_list.count("silly") # 2
fav_words_list.count("womp womp") # 0
```
## Sort
```python
rand_nums = [7, 3, 2, 4,  8, 1, 10, 5, 9]
sorted_nums = sorted(rand_nums)
print(sorted_nums) # [1, 2, 3, 4, 5, 7, 8, 9, 10]
print(rand_nums) # [7, 3, 2, 4, 8, 1, 10, 5, 9]

rand_nums.sort()
print(rand_nums) # [1, 2, 3, 4, 5, 7, 8, 9, 10]

rand_nums.sort(reverse= True)
print(rand_nums) # [10, 9, 8, 7, 5, 4, 3, 2, 1]
```
## Mutable
Lists in python are mutable as you can change the items that the list contains after definition.
Lists point to a location in memory and this location does not change when values are updated:
```python
rand_nums = [7, 3, 2, 4,  8, 1, 10, 5, 9]
id_before = id(rand_nums)
rand_nums += [11, 13, 19, 12]
id_after = id(rand_nums)
print(id_before == id_after) # True
```
Whereas types like integers do not:
```python
some_int = 347
id_before = id(some_int)
some_int += 213
id_after = id(some_int)
print(id_before == id_after) # False
```
So when you set a new variable to a pre-existing list they share the same location in memory:
```python
rand_nums = [7, 3, 2, 4,  8, 1, 10, 5, 9]
sorted_nums = rand_nums
print(id(rand_nums) == id(sorted_nums)) # True
sorted_nums.sort()
print(rand_nums) # [1, 2, 3, 4, 5, 7, 8, 9, 10]
print(sorted_nums) # [1, 2, 3, 4, 5, 7, 8, 9, 10]
```
To circumvent this you can create a copy:
```python
rand_nums = [7, 3, 2, 4,  8, 1, 10, 5, 9]
new_nums = rand_nums.copy()
print(id(rand_nums) == id(new_nums)) # False
new_nums.append(11)
print(rand_nums) # [7, 3, 2, 4,  8, 1, 10, 5, 9]
print(new_nums) # [7, 3, 2, 4,  8, 1, 10, 5, 9, 11]
```
Do keep in mind this is a shallow copy and immutable items will have the same location in both lists:
```python
rand_nums = [[7, 3, 2, 4,  8, 1, 10, 5, 9]]
new_nums = rand_nums.copy()
print(id(rand_nums) == id(new_nums)) # False
print(id(rand_nums[0]) == id(new_nums[0])) # True
new_nums[0].append(11)
print(rand_nums) # [[7, 3, 2, 4, 8, 1, 10, 5, 9, 11]]
print(new_nums) # [[7, 3, 2, 4, 8, 1, 10, 5, 9, 11]]
```
_(`x is y` is the proper syntax to compare but id() does the same thing and works better to illustrate here)_