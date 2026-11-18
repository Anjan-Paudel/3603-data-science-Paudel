# 📝 Worksheet: 01 - Working with Data

Use this worksheet to review and reinforce your understanding of Python's core data containers. Each section ends with an **🤖 Explain It** prompt — write your explanation in your own words, then (optionally) paste it into an AI tutor and ask it to point out anything you got wrong or left out.

---

## 🧠 Section 1: Lists

1. What method adds an item to the end of a list?  
   `Answer:` `.append(item) adds one item to the end of a list.`

2. How can you remove an item from a list by value? By position?  
   `Answer:` ` my_list.remove(value) to remove the first matching value. ` 
   `my_list.pop(index) or del my_list[index] to remove an item at a particular position. pop() `

3. What's the result of this code?

```python
nums = [2, 4, 6]
nums.append(8)
print(nums)
```

   `Answer:` ` [2, 4, 6, 8] `

4. What does `my_list[1:4]` return, given `my_list = [10, 20, 30, 40, 50]`?  
   `Answer:` `[20, 30, 40]`

4a. Given `a = [1, 2]` and `b = [3, 4]`, what is the result of `a + b`? Of `a.append(b)`? Of `a.extend(b)`?  
   `Answer:` `a + b gives a new list [1, 2, 3, 4], leaving a unchanged.`
`a.append(b) changes a to [1, 2, [3, 4]] because b is added as one item.`
`a.extend(b) changes a to [1, 2, 3, 4] because each item from b is added separately.`
`Both .append() and .extend() return None.`

4b. Given `grid = [[1, 2], [3, 4]]`, how do you access the value `3`?  
   `Answer:` `grid[1][0]`

4c. List three different ways to remove an item from a list.  
   `Answer:` `remove(value), pop(index), and del my_list[index]`

---

### ✏️ Task: List Practice

```python
# Create a list of your top 3 favorite foods.
# Add another food to the list.
# Remove one item and print the list.
foods = ["Momo", "Pizza", "Pasta"]
foods.append("Sushi")
foods.remove("Pizza")
print(foods)
```

### ✏️ Task: Slicing and Sorting

```python
# Given: numbers = [42, 17, 8, 99, 23, 4]
numbers = [42, 17, 8, 99, 23, 4]
print(numbers[:3])                      # [42, 17, 8]
print(sorted(numbers))                  # [4, 8, 17, 23, 42, 99]
print(sorted(numbers, reverse=True))    # [99, 42, 23, 17, 8, 4]
# 1. Print the first three numbers using slicing.
# 2. Print the numbers sorted from smallest to largest.
# 3. Print the numbers sorted from largest to smallest.
```

### ✏️ Task: Filtering

```python
# Given: temps = [55, 72, 90, 43, 88, 67, 101]
# Build a new list called "hot" containing only temps over 85.
# Print "hot".
temps = [55, 72, 90, 43, 88, 67, 101]
hot = []
for t in temps:
    if t > 85:
        hot.append(t)
print(hot)  # [90, 88, 101]
```

### ✏️ Task: Combine Lists Three Ways

```python
# Given: morning = ['eggs', 'toast']
#        extras  = ['jam', 'coffee']
# 1. Use + to make a new list "breakfast" without changing "morning".
# 2. On a fresh copy of "morning", use .append(extras) and print the result.
#    Notice how many items the list has now, and why.
# 3. On another fresh copy, use .extend(extras) and print the result.
morning = ['eggs', 'toast']
extras = ['jam', 'coffee']

# 1. + makes a new list without changing morning.
breakfast = morning + extras
print(breakfast)                 # ['eggs', 'toast', 'jam', 'coffee']
print(morning)                   # ['eggs', 'toast']

# 2. append adds the entire extras list as ONE item.
with_append = morning.copy()
with_append.append(extras)
print(with_append)               # ['eggs', 'toast', ['jam', 'coffee']]
print(len(with_append))          # 3

# 3. extend adds each item in extras separately.
with_extend = morning.copy()
with_extend.extend(extras)
print(with_extend)               # ['eggs', 'toast', 'jam', 'coffee']
```

### ✏️ Task: 2D List (grid)

```python
# board = [
#     [1, 2, 3],
#     [4, 5, 6],
#     [7, 8, 9],
# ]
# 1. Print the value in row 2, column 0.
# 2. Change the center value to 0.
# 3. Loop over the board and print each row on its own line.
board = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
]
print(board[2][0])   # 7: row index 2, column index 0
board[1][1] = 0      # change the center value
for row in board:
    print(row)
# [1, 2, 3]
# [4, 0, 6]
# [7, 8, 9]
```

### ✏️ Task: Deleting Items

```python
# Given: queue = ['Ana', 'Ben', 'Cy', 'Dana', 'Eve']
# 1. Remove 'Cy' by value.
# 2. Use .pop() to remove and capture the last person into a variable "served".
# 3. Use del to remove the first person.
# 4. Print the remaining queue and "served".
queue = ['Ana', 'Ben', 'Cy', 'Dana', 'Eve']
queue.remove('Cy')
served = queue.pop()  # remove and capture 'Eve'
del queue[0]          # remove 'Ana'
print(queue)         # ['Ben', 'Dana']
print(served)        # Eve
```

### ✏️ Task: Iterate by Index

```python
# Given: prices = [10, 20, 30, 40]
# 1. Use "for i in range(len(prices)):" to print each item as "0: 10", "1: 20", ...
# 2. Using the index, add 5 to every price in place, then print the list.
# 3. Rewrite step 1 using enumerate() instead.
```

### 🤖 Explain It

In your own words: what's the difference between a list and a slice of a list? Is slicing a list the same as modifying it? And when you write `a.append(b)` versus `a.extend(b)`, what ends up in `a` each way?
`Answer` `A list is an ordered collection of items. A slice is a new list containing only selected items from the original list.` 
`Making a slice does not change the original list by itself. a.append(b) adds b as one item (even if b is a list); a.extend(b) adds the items inside b separately.`

---

## 🔒 Section 2: Tuples

5. What is a key difference between a list and a tuple?  
   `Answer:` `A list is mutable; its items can be changed. A tuple is immutable; its elements cannot be replaced, added, or removed after creation.`

6. Can you change the contents of a tuple once it is created? Why or why not?  
   `Answer:` `You cannot replace elements of a tuple because tuples are immutable.` 
   `However, a mutable object stored inside a tuple (such as a list) can still be changed.`

7. What does `first, *rest = (10, 20, 30, 40)` assign to `first` and `rest`?  
   `Answer:` `first = 10 and rest = [20, 30, 40]. The starred variable collects the remaining values in a list.`

---

### ✏️ Task: Tuple Practice

```python
# Create a tuple with your favorite 3 numbers.
# Unpack it into three variables and print each.
favorite_numbers = (7, 9, 16)
first, second, third = favorite_numbers
print(first)   # 7
print(second)  # 9
print(third)   # 16
```

### ✏️ Task: Unpacking with *rest

```python
# Given: race_times = (9.58, 9.63, 9.69, 9.71, 9.74)
# Unpack this into "winner" (the first time) and "others" (everything else).
# Print both.
race_times = (9.58, 9.63, 9.69, 9.71, 9.74)
winner, *others = race_times
print(winner)  # 9.58
print(others)  # [9.63, 9.69, 9.71, 9.74]
```

### ✏️ Task: Tuples as Dictionary Keys

```python
# Build a dictionary called "distances" where the keys are (city1, city2)
# tuples and the values are the distance in miles between them.
# Add at least two entries, then look up and print one of them.
# Illustrative cities and distances, not real-world measurements.
distances = {
    ("City A", "City B"): 100,
    ("City B", "City C"): 75,
}
print(distances[("City A", "City B")])  # 100
```

### 🤖 Explain It

In your own words: why does Python allow a tuple to be a dictionary key, but not a list? What property makes that possible?
`Dictionary keys must be hashable. A tuple is hashable when all of its elements are hashable, so a tuple of strings can work as a key. Lists are mutable and unhashable, so they cannot be dictionary keys. A tuple containing a list is also unhashable.`

---

## 🔑 Section 3: Dictionaries

8. What does the `.get()` method do differently from accessing a key directly with `[]`?  
   `Answer:` `student.get('gpa') returns None when the key is missing (or a supplied default). student['gpa'] raises a KeyError if that key is missing.`

9. How do you loop through both keys and values in a dictionary?  
   `Answer:` `Use for key, value in my_dict.items():.`

10. How would you remove a key from a dictionary and also capture the value it held?  
    `Answer:` `Use value = my_dict.pop(key).`

11. In a list of dictionaries like `people = [{'name': 'Ana'}, {'name': 'Ben'}]`, how do you get Ben's name?  
    `Answer:` `people[1]['name'] gives 'Ben'.`

12. If the same dictionary object is stored in both a list and another dictionary, and you change it through one, does the other see the change? Why?  
    `Answer:` `Yes. Both containers hold references to the same dictionary object, so a mutation through either reference is visible through the other.`

---

### ✏️ Task: Dictionary Practice

```python
# Create a dictionary with keys: 'name', 'age', and 'hobby'.
# Print each key and value in the format "key: value".
student = {'name': 'Ana', 'age': 21, 'hobby': 'Drawing'}
for key, value in student.items():
    print(f"{key}: {value}")
# name: Ana
# age: 21
# hobby: Drawing
```

### ✏️ Task: Build from Two Lists

```python
# Given: products = ['pen', 'notebook', 'eraser']
#        prices = [1.50, 3.25, 0.75]
# Build a dictionary mapping each product to its price.
# Print the total cost of all products (hint: sum the .values()).
products = ['pen', 'notebook', 'eraser']
prices = [1.50, 3.25, 0.75]
product_prices = {}
for product, price in zip(products, prices):
    product_prices[product] = price
print(product_prices)  # {'pen': 1.5, 'notebook': 3.25, 'eraser': 0.75}
print(f"Total: ${sum(product_prices.values()):.2f}")  # Total: $5.50
```

### ✏️ Task: Nested Dictionaries

```python
# Given:
# inventory = {
#     'apples': {'count': 50, 'price': 0.50},
#     'bananas': {'count': 30, 'price': 0.25},
# }
# Loop through inventory and print a line for each fruit like:
# "apples: 50 units at $0.50"
inventory = {
    'apples': {'count': 50, 'price': 0.50},
    'bananas': {'count': 30, 'price': 0.25},
}
for fruit, details in inventory.items():
    print(f"{fruit}: {details['count']} units at ${details['price']:.2f}")
# apples: 50 units at $0.50
# bananas: 30 units at $0.25
```

### ✏️ Task: List of Dictionaries (table rows)

```python
# roster = [
#     {'name': 'Alex', 'major': 'CS'},
#     {'name': 'Ana',  'major': 'Math'},
#     {'name': 'Ben',  'major': 'History'},
# ]
# 1. Loop over roster and print "name - major" for each student.
# 2. Add a new student record to the list.
# 3. Build and print a list of just the names of everyone majoring in 'CS'.
roster = [
    {'name': 'Alex', 'major': 'CS'},
    {'name': 'Ana',  'major': 'Math'},
    {'name': 'Ben',  'major': 'History'},
]
# 1. Print one name-major pair per student.
for student in roster:
    print(f"{student['name']} - {student['major']}")
# Alex - CS
# Ana - Math
# Ben - History

# 2. Add a student record.
roster.append({'name': 'Maya', 'major': 'CS'})

# 3. Collect names of students majoring in CS.
cs_names = []
for student in roster:
    if student['major'] == 'CS':
        cs_names.append(student['name'])
print(cs_names)  # ['Alex', 'Maya']
```

### ✏️ Task: Update a Record by Row Number

```python
# Using the roster above:
# 1. Build a dict "by_row" mapping each row number to its record
#    (hint: {i: row for i, row in enumerate(roster)}).
# 2. Change the major of the student in row 2 to 'CS'.
# 3. Print roster[2] and explain why it changed too.
# This continues after the roster task above.
by_row = {i: row for i, row in enumerate(roster)}
by_row[2]['major'] = 'CS'
print(roster[2])  # {'name': 'Ben', 'major': 'CS'}
```

### 🤖 Explain It

In your own words: what's the difference between `student['gpa']` and `student.get('gpa')` when `'gpa'` isn't in the dictionary? Which would you use, and when? Also: why does changing `by_row[2]` also change `roster[2]`?
`student['gpa'] gives a KeyError if the key is missing. student.get('gpa') safely returns None, or a default value if I provide one. I use brackets when a key must exist, and .get() when the key may be missing. Updating by_row[2]['major'] also changes roster[2]['major'] because both point to the same student dictionary.`

---

## 🚀 Section 4: Going Further (Optional)

These pair with the "🔥 Challenge" sections in the notebooks — skip if you haven't gotten there yet.

### ✏️ Task: List Comprehension

```python
# Rewrite this loop as a one-line list comprehension:
# cubes = []
# for n in range(6):
#     cubes.append(n ** 3)
cubes = [n ** 3 for n in range(6)]
print(cubes)  # [0, 1, 8, 27, 64, 125]
```

### ✏️ Task: namedtuple

```python
# Create a namedtuple called "Book" with fields "title" and "author".
# Make one instance and print both fields by name.
from collections import namedtuple
Book = namedtuple('Book', ['title', 'author'])
book = Book('Dune', 'Frank Herbert')
print(book.title)   # Dune
print(book.author)  # Frank Herbert
```

### ✏️ Task: Word Counter

```python
# text = "to be or not to be that is the question"
# Build a dictionary counting how many times each word appears.
# (Try it by hand first, then check yourself with collections.Counter.)
text = 'to be or not to be that is the question'
counts = {}
for word in text.split():
    counts[word] = counts.get(word, 0) + 1
print(counts)
# {'to': 2, 'be': 2, 'or': 1, 'not': 1, 'that': 1,
#  'is': 1, 'the': 1, 'question': 1}

from collections import Counter
print(Counter(text.split()))  # Same counts in a Counter object
```

### ✏️ Task: Parse Some JSON

```python
import json
raw = '''
{
  "course": "Programming for Data Science",
  "online": true,
  "instructor": null,
  "students": [
    {"name": "Alex", "grade": 91},
    {"name": "Ana",  "grade": 88}
  ]
}
'''
# 1. Use json.loads(raw) to turn this into Python objects.
# 2. Print the course name and the second student's grade.
# 3. Print the Python type of the value that came from "online" and from "instructor".
data = json.loads(raw)
print(data['course'])              # Programming for Data Science
print(data['students'][1]['grade'])  # 88
print(type(data['online']))       # <class 'bool'>
print(type(data['instructor']))   # <class 'NoneType'>
```

### ✏️ Task: Walk a GeoJSON FeatureCollection

```python
geo = {
    "type": "FeatureCollection",
    "features": [
        {"type": "Feature",
         "geometry": {"type": "Point", "coordinates": [-98.529, 33.878]},
         "properties": {"name": "Bolin Hall"}},
        {"type": "Feature",
         "geometry": {"type": "Point", "coordinates": [-98.531, 33.876]},
         "properties": {"name": "Moffett Library"}},
    ],
}
# Loop over geo["features"] and print each building's name with its
# latitude and longitude. Remember: coordinates are [longitude, latitude].
for feature in geo['features']:
    name = feature['properties']['name']
    longitude, latitude = feature['geometry']['coordinates']
    print(f"{name}: latitude {latitude}, longitude {longitude}")
# Bolin Hall: latitude 33.878, longitude -98.529
# Moffett Library: latitude 33.876, longitude -98.531
```

---

## 🧾 Submit Checklist

- [x] I practiced creating, slicing, sorting, and filtering lists.
- [x] I can explain the difference between `+`, `append()`, and `extend()`.
- [x] I built and traversed a nested (2D) list.
- [x] I removed list items with `remove()`, `pop()`, and `del`.
- [x] I looped by index with `range(len(...))` and with `enumerate()`.
- [x] I understand how tuples are different from lists, and why that makes them hashable.
- [x] I accessed, looped through, updated, and removed items from a dictionary.
- [x] I built a dictionary from two separate lists.
- [x] I worked with at least one nested dictionary.
- [x] I processed a list of dictionaries as table rows and updated a record by row number.
- [x] I parsed JSON with `json.loads()` and walked a GeoJSON FeatureCollection.
- [x] I completed the "Explain It" prompts in my own words.
