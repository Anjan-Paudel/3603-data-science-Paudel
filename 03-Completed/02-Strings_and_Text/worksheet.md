# 📝 Worksheet: 03 - Strings and Text

Use this worksheet to reinforce your understanding of strings — creating them, slicing them, cleaning them up, and formatting them. Each section ends with an **🤖 Explain It** prompt — write your explanation in your own words, then (optionally) paste it into an AI tutor and ask it to point out anything you got wrong or left out.

---

## 🧠 Section 1: String Basics

1. Why doesn't Python care whether you use `'...'` or `"..."`?  
   `Answer:` `Both are str (string) types. The difference is mainly convenience when text contains quotations marks or apostrophes.`

2. What's the output of this code?

```python
word = 'science'
print(word[0:3])
```

   `Answer:` `sci`

3. Rewrite this string so it could be written with single quotes on the outside instead of double:

```python
message = "She said \"don't stop\""
```

   `Answer:` `message = 'She said \"don't stop\"'`

---

### ✏️ Task: Slicing Practice

```python
# Given: course = "Programming for Data Science"
# Print just the word "Data" using slicing.
# Print the string reversed.
```
`print(course[16:20])`
`print(course[::-1])`

### ✏️ Task: Multi-Line String

```python
# Write a triple-quoted string containing a 3-line "About Me" bio.
# Print it.
```
```python
bio = """ My name is Anjan. 
I am 25 years old.
I study Computer Science. """
print(bio) 
```

### 🤖 Explain It

In your own words: why are strings immutable, and what do you actually have to do if you want a "modified" version of a string?
`Answer: Immutable means something cannot be changed directly after it is created. `
`A string cannot be changed character by character , but a variable can be assigned a completely new string.`

---

## 🔁 Section 2: String Methods

4. What's the difference between `.strip()` and `.replace(' ', '')`?  
   `Answer:` `.strip() removes whitespace from beginning and end of a string`
   `.replace(' ' , '') removes every ordinary space from a string. `
   ```python
   name = " Anjan Paudel " 
   print(name.strip())
   print(name.replace(" " , ""))
   ```
   `Anjan Paudel`
   `AnjanPaudel`

5. What will this print?

```python
name = "  ADA lovelace  "
print(name.strip().title())
```

   `Answer:` `Ada Lovelace`

6. If `words = "red,green,blue".split(',')`, what is `words`, and what type is it?  
   `Answer:` `['red' , 'green' , 'blue']` `<class 'list'>`

---

### ✏️ Task: Clean and Validate

```python
# Given: raw_input = "  YES  "
# Clean it up (strip + lowercase) and check if it equals "yes".
# Print True or False.
raw_input = " YES "
cleaned = raw_input.strip().lower()
print(cleaned == "yes")
```


### ✏️ Task: Build a Sentence

```python
# Given: words = ['data', 'science', 'is', 'fun']
# Use .join() to turn this into the sentence "data science is fun".
# Then use .replace() to change "fun" to "powerful" in the result.
words = ['data', 'science', 'is', 'fun']
sentence = " ".join(words)
print(sentence)
sentence = sentence.replace("funs" , "powerful")
print(sentence)
```

### 🤖 Explain It

In your own words: what's the difference between a method like `.upper()` that returns a new string, versus a list method like `.append()` that changes the list in place? Why do strings only work the first way?
`.upper() creates a new string because strings are immutable , meaning they cannot be changed directly`
`.append() changes the original list because lists are mutable`

---

## 🎯 Section 3: Formatted Strings

7. What does the format spec `:.2f` do?  
   `Answer:` `:.2f formats a number to two decimal places and rounds it if needed.`

8. What will this print?

```python
item = "eraser"
qty = 5
print(f"You bought {qty} {item}(s)")
```

   `Answer:` `You bought 5 eraser(s)`

9. Why might you use an f-string instead of `+` to build a string out of variables?  
   `Answer:` `With an f-string , Python handles that formatting for us. ` 
   `F-strings are easier to read and let us put variables directly inside {} without using + or converting numbers to strings. `

---

### ✏️ Task: Formatted Receipt

```python
# Given: item = "Backpack", price = 45.999, qty = 2
# Print a line like: "2x Backpack @ $46.00 = $92.00"
# (Notice price needs rounding — that's what :.2f is for.)

item = "Backpack"
price = 45.999
qty = 2

total = price * qty
print(f"{qty}x {item} @ ${price:.2f} = ${total:.2f}")
```

### ✏️ Task: Aligned Table

```python
# Given: names = ["Ana", "Bartholomew", "Cy"]
# Print each name right-aligned in a 15-character field, one per line,
# so they all line up on the right edge.
names = ["Ana", "Bartholomew", "Cy"]

for name in names:
   print(f"{name:>15}")
```

### 🤖 Explain It

In your own words: what's the practical difference between `f'{price}'` and `f'{price:.2f}'` when `price = 19.999999`? When would the difference actually matter in real code?

`f'{price}' shows the number normally , buit f'{price:.2f}' rounds and displays it to two decimal places.`
`This is useful for prices and reciepts.`

---

## 🚀 Section 4: Going Further (Optional)

These pair with the "🔥 Challenge" sections in the notebooks — skip if you haven't gotten there yet.


### ✏️ Task: Raw String

```python
# Write the Windows path C:\Users\you\Desktop\notes.txt as a raw string.
# Print it, and explain in a comment why the plain (non-raw) version would be risky.

# Raw strings keep backslashes as normal characters.
# Without r , backslashes may be treated as escape sequences.

path = r"C:\Users\you\Desktop\notes.txt"
print(path)
```

### ✏️ Task: Debug Format Spec

```python
# Given: width = 10, height = 4
# Use the f'{expr=}' debug spec to print both "width" and "width * height"
# with their values, without writing separate print() calls for each.
width = 10
height = 4

print(f"{width=} {width * height=}")
# the = inside an f-string shows both the expression and its value. It helps us debug our code. 
```

---

## 🧾 Submit Checklist

- [x] I created strings with single quotes, double quotes, and triple quotes.
- [x] I indexed and sliced a string.
- [x] I used at least three different string methods (`.strip()`, `.split()`, `.join()`, `.replace()`, etc.).
- [x] I built an f-string with more than one embedded expression.
- [x] I used a format spec to control decimal places or alignment.
- [x] I completed the "Explain It" prompts in my own words.
