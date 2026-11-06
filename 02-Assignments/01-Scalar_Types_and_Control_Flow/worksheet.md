# 📝 Worksheet: 02 - Scalar Types and Control Flow

Use this worksheet to reinforce your understanding of variables, arithmetic, comparisons, and decision logic. Each section ends with an **🤖 Explain It** prompt — write your explanation in your own words, then (optionally) paste it into an AI tutor and ask it to point out anything you got wrong or left out.

---

## 🧠 Section 1: Scalar Types and Casting

1. What is the output of the following code?

```python
x = 10
print(type(x))
```

   `Answer:` `<class 'int'>`

2. What scalar type would best represent:
   - A person's name: `str`
   - Their age: `int`
   - Whether they passed a test: `bool`

3. Why does `int('21')` work, but `int('twenty-one')` raise an error?  
   `Answer:` ` int('21') works because it's digit so python can turn it into a number but int('twenty-one) is letters Python cannot translate number words into integers  `

---

### ✏️ Task: Type Practice

```python
# Create a variable for each type and print its value and type.
# Example: an int, float, str, and bool.

age = 25
price = 12.50
name = "Anjan"
passed = True

print(age  , type(age))
print(price, type(price))
print(name, type(name))
print(passed, type(passed))
```

### ✏️ Task: Arithmetic

```python
# Given: hours_worked = 37, hourly_rate = 15.50
# Print the total pay.
# Print the total pay rounded to 2 decimal places (hint: round()).

hours_worked = 40
hourly_rate = 22.50

total_pay = hours_worked * hourly_rate

print(total_pay)
print(round(total_pay, 2))
```

### ✏️ Task: Casting Round Trip

```python
# Given: user_input = "3.14159"
# Convert it to a float, then print it rounded to 2 decimal places.

user_input = "3.14159"

number = float(user_input)

print(round(number, 2))
```

### 🤖 Explain It

In your own words: why does `input()` always return a string, and why does that matter when you want to do math with what the user typed?

---

## 🔁 Section 2: Comparison Operators

4. What does the `!=` operator mean?

   `Answer:` ` != means not equal to check whether two values are different `

5. What will the following code print?

```python
a = 5
b = 3
print(a < b or b < 10)
```

   `Answer:` ` True `

6. What does `0 <= score <= 100` check, and how would you write the same thing *without* chaining?  
   `Answer:` ` It checks score is between 0 and 100 , including 0 and 100 without chaining , we can write ` `score >= 0 and score <=100`

---

### ✏️ Task: Comparison Practice

```python
# Given: temperature = 98.6
# Print True if it's within normal human body temperature range (97.0 to 99.0), else False.
# Try it both as a chained comparison and as two separate comparisons joined with "and".
temp = 98.6
print(97.0 <= temp <= 99.0)
print(temp >= 97.0 and temp <= 99.0)
```

### 🤖 Explain It

In your own words: what's the difference between `=` and `==` in Python? Why does mixing them up cause errors (or worse, silently wrong code)?
`Answer:`  `= assigns the value while == compares two values so using = in if condition cause syntax error but == when i assign a value variable remains unchanged `

**If you've written C++:** explain why `0 <= score <= 100` is safe to write in Python but dangerous to write in C++. What does the C++ version actually evaluate to, and how would you fix it?
` Python checks both comparisions in a chain while c++ evaluates first comparision and then compares its result 0 or 1 with 100 that makes expression true even score outside the range. In c++ i should write score >= 0 && score <= 100. `
---

## 🔀 Section 3: Control Flow

7. Write a conditional that prints "Pass" if a grade is >= 70, and "Fail" otherwise.

```python
# Your code:
grade = 85
if grade >= 70;
   print("pass")
else:
   print("Fail")
```

8. What does `elif` allow you to do that separate `if` statements don't?  
   `Answer:`  ` elif lets me check another condition only if the earlier conditions were false. Only the first matching branch runs. Separate if statements check independently, so more than one branch can run. `

9. What will this print?

```python
age = 16
has_ticket = False
print(age >= 13 and has_ticket)
```

   `Answer:` `Cannot Enter` `False, because age >= 13 is True, but has_ticket is False and operator requires both conditions to be True . `

---

### ✏️ Task: Multi-Branch Logic

```python
# Given: bmi = 22.5
# Print the BMI category:
# "Underweight" (< 18.5), "Normal" (18.5-24.9), "Overweight" (25-29.9), "Obese" (30+)
bmi = 22.5

if bmi < 18.5:
    print("Underweight")
elif bmi < 25:
    print("Normal")
elif bmi < 30:
    print("Overweight")
else:
    print("Obese")
```

### ✏️ Task: Multi-Line Branches

```python
# Given: cart_items = 3, member_since_days = 400
# In the if-branch (member_since_days >= 365): compute a "loyalty discount" of 15%,
#   print the discount amount, and print the final price.
# In the else-branch: print that there's no discount yet, and print the full price.
# Use item_price = 20.00 per item as the starting subtotal.
# Each branch should have at least 3 lines — this is the same shape as the
# "One Branch, Many Lines" example in the notebook.
cart_items = 3
member_since_days = 400
item_price = 20.00

subtotal = cart_items * item_price

if member_since_days >= 365:
    discount = subtotal * 0.15
    final_price = subtotal - discount
    print(f"Discount: ${discount:.2f}")
    print(f"Final price: ${final_price:.2f}")
else:
    final_price = subtotal
    print("No discount yet")
    print(f"Full price: ${final_price:.2f}")
```

### ✏️ Task: Your Turn

Write a program that asks for the weather and prints:
- "Bring sunscreen" if it's sunny
- "Take an umbrella" if it's raining
- "Check the forecast" otherwise
```python
weather = input("What is the weather? ")

if weather == "sunny":
    print("Bring sunscreen")
elif weather == "raining":
    print("Take an umbrella")
else:
    print("Check the forecast")

```
### 🤖 Explain It

In your own words: what's the difference between using `and` versus writing nested `if` statements to check two conditions? Do they always produce the same result?

` And joins two conditions in one if statement. A nested if is an if inside another if. Both can require two conditions to be true, but adding other instructions can change the result. `

---

## 🚀 Section 4: Going Further (Optional)

These pair with the "🔥 Challenge" sections in the notebooks — skip if you haven't gotten there yet.

### ✏️ Task: Conditional Expression

```python
# Rewrite this as a one-line conditional expression:
# if temperature > 90:
#     comfort = "too hot"
# else:
#     comfort = "fine"

temperature = 92
comfort = "too hot" if temperature > 90 else "fine"
print(comfort)
```

### ✏️ Task: Float Precision

```python
# Predict, then check: does 0.1 + 0.1 + 0.1 == 0.3 evaluate to True or False in Python?
# Write a "close enough" check instead of using == directly.
# Prediction: False

# Check:
total = 0.1 + 0.1 + 0.1
print(total == 0.3)

# Close enough check:
print(abs(total - 0.3) < 0.000000001)
```

### ✏️ Task: Match Statement

```python
# Given: grade_letter = 'B'
# Use match/case to print:
#   "Excellent" for 'A'
#   "Good" for 'B' or 'C'
#   "Needs improvement" for anything else (use the "_" wildcard case)

grade_letter = 'B'

match grade_letter:
    case 'A':
        print("Excellent")
    case 'B' | 'C':
        print("Good")
    case _:
        print("Needs improvement")
```

### 🤖 Explain It

**If you've written C++:** how is Python's `match`/`case` similar to a C++ `switch`? What can `match` do (strings, multiple values per case with `|`) that a plain C++ `switch` can't?

`Answer: ` ` Python’s match and C++’s switch both pick which code to run based on a value. Python can match text and use | for choices like 'B' or 'C'. C++’s switch cannot check strings directly, and it needs separate case labels for different choices. `


---

## 🧾 Submit Checklist

- [x] I practiced creating and casting each scalar type.
- [x] I used arithmetic operators, including `//` and `%`.
- [x] I wrote conditionals using comparison and logical operators.
- [x] I used a chained comparison at least once.
- [x] I wrote at least one branch with multiple lines inside it.
- [x] I completed the "Explain It" prompts in my own words.
