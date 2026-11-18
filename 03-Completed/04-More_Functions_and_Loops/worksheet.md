# 📝 Worksheet: 04 - More Functions & Loops

Do this worksheet **on paper, without a computer**. Each section ends with an **🤖 Explain It** prompt: write your explanation in your own words, then (optionally) paste it into an AI tutor and ask it to point out anything you got wrong or left out.

---

## 🧠 Section 1: Defaults and Keywords

```python
def price(amount, tax=0.0825, discount=0):
    return round(amount * (1 + tax) - discount, 2)
```

What does each call return?

1. `price(100)` → 108.25
2. `price(100, discount=10)` → 98.25
3. `price(100, 0)` → 100.0
4. `price(discount=5, amount=20)` → 16.65

> 🤖 **Explain It:** Why are keyword arguments easier to read than positional ones in a call like `price(100, 0, 10)`?

---

## 🧠 Section 2: Scope

What prints? Explain why.

```python
count = 0

def add_one(count):
    count = count + 1
    return count

result = add_one(count)
print(count, result)
```

`Answer:` ` 0 1 `

> 🤖 **Explain It:** Describe the "room with two doors" model of a function in your own words.
` A function is like a room with two doors. Parameters bring information inside, and return sends the result outside. Local variables stay inside the function and do not directly change variables outside. `

---

## 🧠 Section 3: Trace a While Loop

```python
balance = 100
years = 0
while balance < 150:
    balance = balance + 20
    years += 1
```

| pass | `balance` at the start | `balance < 150`? | `balance` after | `years` after |
|------|------------------------|------------------|-----------------|---------------|
| 1 | 100 | True | 120 | 1 |
| 2 | 120 | True | 140 | 2 |
| 3 | 140 | 160 | | 3 |
| 4 | 160 | False | 160 | 3 |

Final `years`:  3   Final `balance`: 160

What single change would make this an **infinite** loop?  
`Answer:` `Remove balance = balance + 20. The balance would stay at 100, so the condition would always be True.`

---

## 🧠 Section 4: `for` or `while`?

| Task | `for` or `while`? | Why? |
|------|-------------------|------|
| Print each line of a file | for | Goes through each line |
| Keep asking for a password until it's correct | 	while | Repeats until the password is correct |
| Find the average of a list of prices | 	for | Goes through each price |
| Double a number until it's over one million |	while | Repeats until the number passes the limit |

---

## 🧠 Section 5: Files

Given the file `pets.txt`:

```text
name,species
Rex,dog

# rescued in May
Tom,cat
```

1. How many times does `for line in f:` run? ` 5 times `
2. Which lines should your code skip, and how would you detect each one?  
   `Answer:` `Skip the header using line == "name,species", blank lines using line.strip() == "", and comments using line.startswith("#") after stripping whitespace.`
3. Write the list of dictionaries a `read_pets` function should return:  
   `[{"name": "Rex", "species": "dog"}, {"name": "Tom", "species": "cat"}]`

> 🤖 **Explain It:** When is `try` / `except` a good idea, and when does it just hide bugs?
`try / except is useful when handling expected errors, like a missing file or invalid number. It hides bugs when we catch every error without understanding or fixing the problem.`
