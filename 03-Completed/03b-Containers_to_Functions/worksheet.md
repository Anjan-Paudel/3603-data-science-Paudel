# 📝 Worksheet: 03b - Containers → Functions

Do this worksheet **on paper, without a computer**. The point is to practice being the computer. Each section ends with an **🤖 Explain It** prompt: write your explanation in your own words, then (optionally) paste it into an AI tutor and ask it to point out anything you got wrong or left out.

---

## 🧠 Section 1: Trace a Loop

Fill in the table for this code:

```python
temps = [31, 45, 28, 52]
total = 0
count = 0
for t in temps:
    total += t
    if t <= 32:
        count += 1
```

| pass | `t` | `total` | `count` |
|------|-----|---------|---------|
| start | — | 0 | 0 |
| 1 |31 | 31 | 1 |
| 2 | 45 | 76 | 1 |
| 3 | 28 | 104 | 2 |
| 4 | 52 | 156 | 2 |

Which **two** patterns are mixed together in this loop?  
`Answer:` ` Accumulate and Count. `

> 🤖 **Explain It:** Explain the difference between Accumulate, Count, and Filter as if you were talking to someone who has never programmed.
` Accumulate adds values together to get a total. Count checks a condition and counts how many items pass. Filter creates a new list containing only items that meet a condition. `

---

## 🧠 Section 2: Pick Your Weapon

| Scenario | Container | Why? |
|----------|-----------|------|
| Daily step counts for a month | List | Stores multiple daily counts in order |
| A playing card (rank, suit) | Tuple | Holds two fixed values together |
| Username → password hash | Dictionary | 	Connects each username to its password hash |
| Every distinct IP address in a log file | Set | 	Stores unique IP addresses without duplicates |
| Your class schedule, in order | List | 	Keeps classes in their scheduled order |

> 🤖 **Explain It:** Pick the scenario you were *least* sure about and argue for a different container than the one you chose.
` I chose a tuple for a playing card because its rank and suit are fixed. A dictionary could also work by storing "rank" and "suit" as keys, making it easier to identify each value. `

---

## 🧠 Section 3: Take It Apart

```python
course = {
    "title": "CMPS 3603",
    "students": [
        {"name": "Ana", "scores": [88, 92]},
        {"name": "Ben", "scores": [75, 81]}
    ]
}
```

Write the value after **each** step:

1. `course["students"]` → ` [{"name": "Ana", "scores": [88, 92]}, {"name": "Ben", "scores": [75, 81]}] `
2. `course["students"][1]` → ` {"name": "Ben", "scores": [75, 81]} `
3. `course["students"][1]["scores"]` → ` [75, 81] `
4. `course["students"][1]["scores"][0]` → ` 75 `

Write the expression that gets Ana's second score:  
`Answer:` ` course["students"][0]["scores"][1] `
` Output: 92 `

---

## 🧠 Section 4: Functions

1. What prints?

```python
def f(x):
    return x + 1

print(f(f(f(0))))
```

   `Answer:` ` 3 `

2. What prints? Explain why.


```python
def shout(word):
    print(word.upper())

x = shout("hi")
print(x)
```

   `Answer:` `HI` `None` ` The function prints HI using print(), but it does not return anything, so x becomes None. `

3. Circle the **parameters** and underline the **arguments**:

```python
def greet(name, greeting):
    return greeting + ", " + name

greet("Ada", "Hello")
```

> 🤖 **Explain It:** In your own words, explain `print()` vs. `return`. Then explain why getting it wrong breaks a pipeline.
` print() displays a value, while return sends a value back to the caller. A pipeline needs return to pass data to the next function. Using only print() can break a pipeline because the function returns None. `

---

## 🧠 Section 5: Contracts and Tests

Write a contract for a function `longest_word(words)`:

```text
IN: A list of strings.
OUT: The longest string, or None if empty.
DOES: Finds and returns the longest word. If tied, returns the first one
```

Write one test of each kind:

- Normal: longest_word(["cat", "elephant", "dog"]) # Expected: "elephant
- Boundary: longest_word(["hi"]) # Expected: "hi"
- Weird: longest_word([]) # Expected: None

---

## 🧠 Section 6: Draw the Pipeline

> "Given a list of prices, drop any that are `0` or less, add 8.25% tax to each, then find the total."

1. Name each function you'd need.
2. For each one, write what goes **in** and what comes **out** (shape, not just "data").
3. Draw the pipeline with arrows, labeling each arrow with the data's shape.

Function	    IN	            OUT
keep_positive	List of prices	List of positive prices
add_tax	List of prices	List of taxed prices
calculate_total	List of prices	Number (total cost)

      Prices
   (List of numbers)
         |
         v
   keep_positive()
     (List → List)
         |
         v
      add_tax()
     (List → List)
         |
         v
   calculate_total()
    (List → Number)
         |
         v
      Final Total
       (Number)

> 🤖 **Explain It:** Why is a pipeline of small functions easier to fix than one big block of code?
` A pipeline of small functions is easier to fix because each function does one job. If something goes wrong, we can find and fix the problem without changing the whole program. Small functions are also easier to test and reuse. `
