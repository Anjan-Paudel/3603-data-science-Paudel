# 📝 Quiz: 04 - More Functions & Loops

16 questions covering default and keyword arguments, returning tuples, scope, `while` loops, `break` / `continue`, and reading files. Mix of multiple choice, true/false, code-tracing, and short answer.

Try every question on your own first. The Answer Key is at the bottom, so don't peek. If you're using an AI tutor, paste in *your answer* and ask it to check your reasoning, rather than asking it to solve the question for you.

---

## Section A — Function Extras

**1.** (Code Tracing) What prints?
```python
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

print(greet("Ada"))
print(greet("Ada", "Hi"))
```
`Hello, Ada!`
`Hi, Ada!`

**2.** (True/False) `def f(a=1, b):` is a valid function definition.
`False`

**3.** (Code Tracing) What prints?
```python
def describe(name, major="Undeclared"):
    return f"{name} — {major}"

print(describe(major="Art", name="Ben"))
```
`Ben - Art`

**4.** (Short Answer) In `sorted(scores, reverse=True)`, what kind of argument is `reverse=True`, and what does that tell you about how `sorted` was written?
` reverse=True is a keyword argument.`
`It tells us that sorted() has a parameter named reverse with a default value, which we override to sort in descending order.`

**5.** (Code Tracing) What prints?
```python
def low_high(nums):
    return min(nums), max(nums)

result = low_high([4, 8, 1])
print(result)
```
`(1,8)`

**6.** (Code Tracing) What prints?
```python
x = 5

def f():
    x = 100
    return x

print(f(), x)
```
`100 5`

**7.** (Short Answer) Why should a function get its data through parameters instead of reading a global variable?
`Parameters make functions easier to understand, test, and reuse. They also prevent bugs caused by depending on global variables that may change.`
---

## Section B — While Loops

**8.** (Short Answer) Name the three parts every `while` loop needs.
`Start: Initialize the variable.`
`Condition: Decide when the loop runs.`
`Update: Change the variable so the loop eventually stops.`

**9.** (Code Tracing) What prints?
```python
n = 1
while n < 20:
    n = n * 2
print(n)
```
`32`

**10.** (Multiple Choice) Which situation is the best fit for a `while` loop?
A) Print every name in a list  
B) Add up every score in a list  
C) Keep rolling a die until you get a 6  
D) Count the vowels in a word
` Answer: C) Keep rolling a die until you get a 6 `

**11.** (Code Tracing) What prints?
```python
for s in [80, 55, 90, 40]:
    if s < 60:
        break
    print(s)
```
`80`

**12.** (Code Tracing) What prints?
```python
for s in [80, 55, 90, 40]:
    if s < 60:
        continue
    print(s)
```
`80`
`90`

---

## Section C — Files

**13.** (Short Answer) What does `with` guarantee when you open a file with `with open("data.txt") as f:`?
`Answer` `with automatically closes the file when the block finishes, even if an error occurs inside the block.`

**14.** (Code Tracing) What is the value?
```python
line = "Bob,84\n"
line.strip().split(",")
```
`Answer` `['Bob', '84']`

**15.** (Short Answer) Why do lines print with an extra blank line between them when you `print(line)` inside `for line in f:`?
`Answer` `Each line in a file already ends with \n, and print() adds another newline. This creates an extra blank line.`

**16.** (Code Tracing) What prints if `missing.txt` doesn't exist?
```python
try:
    with open("missing.txt") as f:
        print("opened")
except FileNotFoundError:
    print("no file")
print("done")
```
`no file`
`done`
