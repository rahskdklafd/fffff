
import requests 
import json

API_KEY = "gsk _bv6aoIWNeZ93DGFoyRZ6WGdyb3FYLhLERRX2Yb4X59IAGTjnRJCz" 
URL = "https://api.groq.com/openai/v1/chat/completions"

SYSTEM_PROMPT = """ You are a Machine Learning and Data Analysis coding assistant.

RESPONSE FORMAT RULES
• Always return ONLY Python code.
• Code must be clean, readable, and properly formatted.
• Preserve indentation and line breaks.
• Add short comments explaining each step.
• The code must run directly in Python or Jupyter Notebook.
• Never compress code into one line.
• Never include explanations outside the code.

BEHAVIOR RULES

1. If the user sends a FULL QUESTION or DATA ANALYSIS TASK:
Return a complete runnable pipeline with comments and an example.

Structure must follow this order:

# Step 1 - Imports
# Step 2 - Example data creation or data loading
# Step 3 - Data preprocessing / cleaning
# Step 4 - Data analysis or transformation
# Step 5 - Result output

2. If the user asks about a SPECIFIC TASK:
Return ONLY the relevant code snippet with a small example dataset.

Example cases:
• scaling features
• groupby operation
• filtering
• numpy slicing
• merging datasets

3. If the user sends BUGGY CODE or an ERROR:
Return the corrected version of the code.

Requirements:
• Fix the bug directly in the code
• Add a comment marking the fix

Example comment:
# FIX: corrected column name

Do NOT explain the error outside the code.

PRIMARY TOPICS (Focus areas)

NUMPY
• Arrays
• Indexing and slicing
• Boolean masking
• Vector operations
• Numerical operations
• Matrix operations

PANDAS / DATA ANALYSIS (DVA Python)
• Data loading
• Data cleaning
    - handling duplicates
    - handling blanks
    - fixing inconsistent data types
• Data filtering
• Data grouping
• Data merging
• Data pivoting
• Data aggregation

EXAMPLE RULE

If the user asks:
"How to filter rows where age > 30?"

Return code like this:

import pandas as pd

# Example dataset
data = {
    "Name": ["Alice","Bob","Charlie"],
    "Age": [25,35,40]
}

df = pd.DataFrame(data)

# Filter rows where age > 30
filtered_df = df[df["Age"] > 30]

print(filtered_df)

Always include a small working example unless the user provides their own dataset. """

def ask(question):

    payload = {
        "model": "openai/gpt-oss-120b",
        "messages": [
            {"role": "system", "content": SYSTEM_PROMPT},
            {"role": "user", "content": question}
        ],
        "temperature": 0
    }

    headers = {
        "Authorization": f"Bearer {API_KEY}",
        "Content-Type": "application/json"
    }

    response = requests.post(URL, headers=headers, data=json.dumps(payload))

    result = response.json()

    return result["choices"][0]["message"]["content"]
to ask any question use this function

print(ask("explain full logistic regression"))

            OR
from IPython.display import Markdown

Markdown(ask("explain full logistic regression"))

api keys:-

lucknow:-

gsk _AF0idVsqN8Of4EUXd9w8WGdyb3FY7XMH59c3q8PqAEjzmincpplt
gsk _YAO0UFNe0jA6bJTdCGPXWGdyb3FY52UNm0QD8pM16XawU5lxZtP0
bihar:-

gsk _929p2Xcx2GEgk7Ei3mfSWGdyb3FYlrhO4qOEeolCWY9FGjef5LAr
gsk _WrDVVe1xJfByy5wPd0lEWGdyb3FYCKfSL8cJBa5etMvxe0RibOle
gsk _FZV9qjwkd7UGUi3JT8h1WGdyb3FY01Ljfjmgdep8hyor2qgzYUld
muzafar:-

gsk _PRNGNpPf3V8jC83JGL34WGdyb3FYUqlkcmoO5qHljzNQbgJngsds
gsk _tlbP2oGKa6guVQ55e2L1WGdyb3FYijfvxsntUq8zg3IxFxmtabbe
ravi:-

gsk _3gEK5dlq63QVsTqf6KJHWGdyb3FYdu3dBNVTJXxuxDfuYy7L0Umb
gsk _dmZqtBSrYQpa9lerxcawWGdyb3FYqONboiRU9fbmrXsLhlLGbvFV
gsk _FCZYeSiUHJuXk89NI0tNWGdyb3FYSRNT2D2IZmuqK5WklASf67F5
rj18:-

gsk _SeZnfHSDLDKzGI2AONGnWGdyb3FYsyzCQswy7ZzwtJygMgIJ9kLj
gsk _aMJcXIQGUskh48AQJy3UWGdyb3FYBNlcMp01VI5KkNpxBf9Qt8io
gsk _CrUJuztwGeYCrYGUr6BnWGdyb3FYhKVsaadyUbQt2XcmadQI10Uk
gsk _AyIvNjKV3A3VvLAatGgHWGdyb3FY2rG9N0mdhnRrLuBCuXB891cR
meerut :-

gsk _W3Vz8vG8FyagTQZCv9E1WGdyb3FYixbjWPKyTVWjKEJ29vmYAIJR
gsk _H2XtLooHca8yrhfto70EWGdyb3FYQpJ0i4ghy1eqjWEFGYLMvtUv
gsk _Osa4dsWpRdy226YuZJ7BWGdyb3FYD2XSnk68fiaH6Alnl8yrsDq6
gsk _PRGvuTOjnfdT1J38pmN3WGdyb3FYn6cn5DcxOmB5dOgDwRqGo09t
gg:-

gsk _a91hAqQemMJAhd5pLo7PWGdyb3FYXiMr7hIglEh8IkwZsvojuqf7
gsk _ctpHZh2ExLGS3YApy0SSWGdyb3FY8b7W8v00aKH3ew0o4SmzKeOg
gsk _rkBWZ5OtATuCcrIM5FBgWGdyb3FYWU1bGcwCfLsPiadcxh23iEve
gsk _StHQNysPV0fi3sbxF0NbWGdyb3FYQNHERSSNhnkAPpCXcbw72q5s
dadri:-

gsk _Fvj9HrCWL8d275AwPnrDWGdyb3FYy1gcNf1Rve8lyFEiwQYe0h1v
gsk _W5X9Ajno6LZtkkh18UBfWGdyb3FYtBlJMF13aimdwSlOTT9iOEAL
gsk _XPPxnfQzinh4hhbWY7vkWGdyb3FYIQ7ou7kU8uX46c0Kv1PiV0Ms
gsk _fAyEpM2GDrxGDDZaYSRaWGdyb3FYkEYNoIi06PfHy0HywGKxwZrN
mandi:-

gsk _Cer3BjVGmXpc9nck5WhsWGdyb3FYMgYZbplJ9rLI3YxmZnynQxYR
gsk _CVq2n8pjJUDTXQaauyikWGdyb3FYTQXoLaIm1s6UZGtfI5xRLp6C
gsk _wSdZpchzW9Ysb9KWteaqWGdyb3FYquPvt3nXnxXX9jcWhvmtjvxl


---

## 📋 Table of Contents

- [🏗️ CREATION](#️-creation)
- [🔍 PROPERTIES](#-properties)
- [🔄 RESHAPING](#-reshaping)
- [➕ MATH](#-math)
- [📊 STATS](#-stats)
- [🔎 SEARCHING](#-searching)
- [🔀 SORTING](#-sorting)
- [🔗 JOIN & SPLIT](#-join--split)
- [✅ LOGIC](#-logic)
- [🔢 LINEAR ALGEBRA](#-linear-algebra)
- [🎲 RANDOM](#-random)

---

## 🏗️ CREATION

---

### `np.array()`
> Create an array from a Python list or nested list.

```python
import numpy as np

# Example 1 — 1D array
a = np.array([1, 2, 3, 4])
print(a)        # [1 2 3 4]
print(type(a))  # <class 'numpy.ndarray'>

# Example 2 — 2D array (matrix)
b = np.array([[1, 2, 3], [4, 5, 6]])
print(b.shape)  # (2, 3)

# Example 3 — Mixed types get upcasted
c = np.array([1, 2, 3.5])
print(c.dtype)  # float64  ← integers become floats!
```

> ⚠️ **Exam Traps:**
> - `np.array([1, 2, 3.0])` → dtype is `float64`, NOT `int64` (upcasting!)
> - `np.array([[1,2],[3]])` → creates an object array, NOT a 2D matrix (unequal rows)
> - `np.array(5)` → creates a 0-dimensional array (scalar array), shape is `()`

---

### `np.zeros()`
> Create an array filled with 0s.

```python
# Example 1 — 1D
a = np.zeros(5)
print(a)        # [0. 0. 0. 0. 0.]
print(a.dtype)  # float64  ← default is float!

# Example 2 — 2D
b = np.zeros((3, 4))
print(b.shape)  # (3, 4)

# Example 3 — Integer zeros
c = np.zeros((2, 2), dtype=int)
print(c.dtype)  # int64
```

> ⚠️ **Exam Traps:**
> - Default dtype is `float64`, not `int` → `np.zeros(3)` gives `[0. 0. 0.]`
> - Shape must be a **tuple** for 2D: `np.zeros((3,4))` ✅ — `np.zeros(3,4)` ❌ (error)

---

### `np.ones()`
> Create an array filled with 1s.

```python
# Example 1
a = np.ones((2, 3))
# [[1. 1. 1.]
#  [1. 1. 1.]]

# Example 2 — Use to initialize weights
weights = np.ones(5) * 0.2   # [0.2 0.2 0.2 0.2 0.2]

# Example 3 — dtype control
c = np.ones((2, 2), dtype=bool)
# [[ True  True]
#  [ True  True]]
```

> ⚠️ **Exam Traps:**
> - Same as zeros — default dtype is `float64`
> - `np.ones(3) * 5` gives `[5. 5. 5.]` (float, not int)

---

### `np.full()`
> Create an array filled with a constant value.

```python
# Example 1
a = np.full((2, 3), 7)
# [[7 7 7]
#  [7 7 7]]

# Example 2 — Fill with float
b = np.full(4, 3.14)
# [3.14 3.14 3.14 3.14]

# Example 3 — Fill with string
c = np.full(3, "hello")
# ['hello' 'hello' 'hello']
```

> ⚠️ **Exam Traps:**
> - `np.full((2,3), 7)` → dtype inferred from `7` → `int64`
> - `np.full((2,3), 7.0)` → dtype is `float64`

---

### `np.arange()`
> Like Python `range()` but returns an ndarray.

```python
# Example 1 — Basic
a = np.arange(5)         # [0 1 2 3 4]

# Example 2 — Start, stop, step
b = np.arange(1, 10, 2)  # [1 3 5 7 9]

# Example 3 — Float step
c = np.arange(0, 1, 0.2) # [0.  0.2 0.4 0.6 0.8]
```

> ⚠️ **Exam Traps:**
> - Stop is **exclusive**: `np.arange(1, 5)` → `[1 2 3 4]` (no 5!)
> - With float steps, count can be unpredictable due to floating point — prefer `np.linspace`
> - `np.arange(5)` → dtype `int64`; `np.arange(5.0)` → dtype `float64`

---

### `np.linspace()`
> Create N evenly spaced values between start and stop (**inclusive** by default).

```python
# Example 1
a = np.linspace(0, 1, 5)
# [0.   0.25 0.5  0.75 1.  ]

# Example 2 — Exclude endpoint
b = np.linspace(0, 1, 5, endpoint=False)
# [0.  0.2 0.4 0.6 0.8]

# Example 3 — Common use: plotting
x = np.linspace(-np.pi, np.pi, 100)
y = np.sin(x)
```

> ⚠️ **Exam Traps:**
> - `np.linspace(0, 1, 5)` → **5 points**, not 5 intervals! Spacing = 0.25
> - **Stop IS included** (unlike `arange`) → `np.linspace(0,1,5)` ends at `1.0`
> - 3rd argument is **number of points**, not step size

---

### `np.eye()`
> Create a 2D identity matrix (1s on diagonal, 0s elsewhere).

```python
# Example 1 — Square identity
a = np.eye(3)
# [[1. 0. 0.]
#  [0. 1. 0.]
#  [0. 0. 1.]]

# Example 2 — Rectangular
b = np.eye(3, 4)
# [[1. 0. 0. 0.]
#  [0. 1. 0. 0.]
#  [0. 0. 1. 0.]]

# Example 3 — Off-diagonal
c = np.eye(3, k=1)
# [[0. 1. 0.]
#  [0. 0. 1.]
#  [0. 0. 0.]]
```

> ⚠️ **Exam Traps:**
> - Default dtype is `float64`
> - `k` shifts the diagonal: `k=1` → above main diagonal, `k=-1` → below

---

### `np.identity()`
> Always creates a **square** identity matrix.

```python
a = np.identity(4)
# 4x4 identity matrix

# Difference from eye:
np.identity(3)        # square only
np.eye(3, 4)          # can be rectangular ← eye is more flexible
```

> ⚠️ **Exam Traps:**
> - `np.identity` only takes one argument (n) — cannot make rectangular matrices
> - Both `eye` and `identity` default to `float64`

---

### `np.empty()`
> Allocate array **without initializing** values (garbage values).

```python
a = np.empty((2, 3))
# Values are whatever was in memory — unpredictable!
# e.g. [[6.23e-307, 0., 0.], [0., 0., 0.]]
```

> ⚠️ **Exam Traps:**
> - Do NOT assume values are zero — they're random memory garbage
> - Faster than `zeros` but dangerous if you forget to fill it

---

### `np.tri()`
> Lower triangle matrix of 1s.

```python
a = np.tri(3)
# [[1. 0. 0.]
#  [1. 1. 0.]
#  [1. 1. 1.]]

b = np.tri(3, k=1)   # include 1 diagonal above main
# [[1. 1. 0.]
#  [1. 1. 1.]
#  [1. 1. 1.]]
```

> ⚠️ **Exam Traps:**
> - `np.tri` fills **lower** triangle (including diagonal) with 1s
> - `k=0` is default (main diagonal); positive k includes more, negative includes less

---

## 🔍 PROPERTIES

---

### `.shape`
> Returns a tuple of array dimensions.

```python
a = np.array([[1,2,3],[4,5,6]])
print(a.shape)   # (2, 3)  → 2 rows, 3 cols

b = np.array([1, 2, 3])
print(b.shape)   # (3,)  ← note: tuple with one element

c = np.array(5)
print(c.shape)   # ()  ← 0-dimensional scalar
```

> ⚠️ **Exam Traps:**
> - 1D array shape is `(n,)` not `(1, n)` or `(n)`
> - `(3,)` ≠ `(3,1)` ≠ `(1,3)` — these behave differently in operations!

---

### `.ndim`
> Number of dimensions (axes).

```python
a = np.array([1,2,3])           # ndim = 1
b = np.array([[1,2],[3,4]])     # ndim = 2
c = np.zeros((2,3,4))           # ndim = 3
print(a.ndim, b.ndim, c.ndim)   # 1 2 3
```

> ⚠️ **Exam Traps:**
> - `np.array(5).ndim` → `0` (scalar array has 0 dimensions)

---

### `.size`
> Total number of elements.

```python
a = np.zeros((3, 4))
print(a.size)    # 12  (= 3 × 4)

b = np.zeros((2,3,4))
print(b.size)    # 24  (= 2 × 3 × 4)
```

> ⚠️ **Exam Traps:**
> - `.size` is the **product** of all shape dimensions
> - Don't confuse with `len(a)` → `len` returns only first dimension = 3 for shape (3,4)

---

### `.dtype`
> Data type of array elements.

```python
a = np.array([1, 2, 3])
print(a.dtype)    # int64

b = np.array([1.0, 2.0])
print(b.dtype)    # float64

c = np.array([True, False])
print(c.dtype)    # bool
```

> ⚠️ **Exam Traps:**
> - `np.array([1, 2, 3.0]).dtype` → `float64` (upcasting!)
> - `np.array([1, 2, True]).dtype` → `int64` (True=1, False=0)
> - `np.array([1, 2, "3"]).dtype` → `<U21` (string, everything becomes string!)

---

### `.astype()`
> Cast array to a different dtype.

```python
a = np.array([1.7, 2.9, 3.1])

b = a.astype(int)
print(b)   # [1 2 3]  ← TRUNCATES, does not round!

c = a.astype(bool)
print(c)   # [ True  True  True]  ← 0.0 → False, else True

d = np.array(["1","2","3"]).astype(float)
print(d)   # [1. 2. 3.]
```

> ⚠️ **Exam Traps:**
> - `float → int` **truncates** (floors toward zero), does NOT round: `1.9 → 1`
> - `0 → bool` is `False`; any nonzero → `True`
> - `astype` returns a **copy**, not in-place modification

---

### `.itemsize`
> Size in bytes of one element.

```python
a = np.array([1,2,3], dtype=np.int32)
print(a.itemsize)   # 4 bytes

b = np.array([1.0], dtype=np.float64)
print(b.itemsize)   # 8 bytes
```

> ⚠️ **Exam Traps:**
> - `int64` → 8 bytes, `int32` → 4 bytes, `float32` → 4 bytes, `float64` → 8 bytes

---

### `.nbytes`
> Total memory used by array in bytes.

```python
a = np.zeros((3, 4), dtype=np.float64)
print(a.nbytes)   # 96  (= 3*4*8 bytes)

# Formula: nbytes = size × itemsize
print(a.size * a.itemsize)  # 96
```

---

## 🔄 RESHAPING

---

### `np.reshape()`
> Change the shape without changing the data.

```python
# Example 1
a = np.arange(12)
b = a.reshape(3, 4)
print(b.shape)   # (3, 4)

# Example 2 — Use -1 to auto-calculate one dimension
c = a.reshape(4, -1)   # NumPy figures out 3
print(c.shape)   # (4, 3)

# Example 3 — 3D reshape
d = a.reshape(2, 2, 3)
print(d.shape)   # (2, 2, 3)
```

> ⚠️ **Exam Traps:**
> - Total elements must match: `12 elements → (3,4) ✅ (3,5) ❌`
> - `-1` can only be used **once** in reshape
> - `reshape` returns a **view** when possible (modifying it may modify original!)

---

### `.flatten()`
> Collapse to 1D — always returns a **copy**.

```python
a = np.array([[1,2,3],[4,5,6]])
b = a.flatten()
print(b)   # [1 2 3 4 5 6]

b[0] = 99
print(a[0,0])   # 1  ← original unchanged (it's a copy)
```

> ⚠️ **Exam Traps:**
> - `.flatten()` = **copy** (safe to modify)
> - `.ravel()` = **view** when possible (modifying may change original!)

---

### `.ravel()`
> Flatten to 1D — returns a **view** if possible.

```python
a = np.array([[1,2],[3,4]])
b = a.ravel()
b[0] = 99
print(a)   # [[99  2]  ← original changed! (view)
           #  [ 3  4]]
```

> ⚠️ **Exam Traps:**
> - Key difference from `flatten`: `ravel` is a view → modifying it changes original
> - Not always a view (depends on memory layout), but treat it as one

---

### `.T` / `np.transpose()`
> Transpose array (swap axes).

```python
a = np.array([[1,2,3],[4,5,6]])  # shape (2,3)
b = a.T
print(b.shape)   # (3,2)

# 1D stays 1D!
c = np.array([1,2,3])
print(c.T.shape)  # (3,)  ← NO CHANGE for 1D!
```

> ⚠️ **Exam Traps:**
> - **Transposing a 1D array does nothing!** `(3,)` stays `(3,)` not `(3,1)`
> - To make column vector: `c.reshape(-1,1)` or `c[:, np.newaxis]`

---

### `np.expand_dims()`
> Add a new axis of size 1.

```python
a = np.array([1,2,3])   # shape (3,)

b = np.expand_dims(a, axis=0)   # shape (1,3) ← row vector
c = np.expand_dims(a, axis=1)   # shape (3,1) ← column vector

print(b.shape, c.shape)  # (1, 3)  (3, 1)
```

> ⚠️ **Exam Traps:**
> - `axis=0` adds dim at the front; `axis=1` adds in second position
> - Equivalent to `a[np.newaxis, :]` or `a[:, np.newaxis]`

---

### `np.squeeze()`
> Remove axes of size 1.

```python
a = np.array([[[1,2,3]]])  # shape (1,1,3)
b = np.squeeze(a)
print(b.shape)   # (3,)

c = np.zeros((3,1,4))
print(np.squeeze(c).shape)  # (3,4)
```

> ⚠️ **Exam Traps:**
> - Only removes dimensions of size **1** — won't touch (3,4) axes
> - `squeeze(axis=1)` removes only the specified axis (error if not size 1)

---

## ➕ MATH

---

### `np.add()`, `np.subtract()`, `np.multiply()`, `np.divide()`
> Element-wise arithmetic.

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(np.add(a, b))       # [5 7 9]
print(np.subtract(a, b))  # [-3 -3 -3]
print(np.multiply(a, b))  # [4 10 18]
print(np.divide(a, b))    # [0.25 0.4  0.5 ]
```

> ⚠️ **Exam Traps:**
> - `np.divide` always returns `float64`
> - `a / b` is same as `np.divide(a,b)` but `a // b` is floor division
> - Integer division `np.divide([5],[2])` → `[2.5]` NOT `[2]`

---

### `np.power()`
> Element-wise exponentiation.

```python
a = np.array([2, 3, 4])
print(np.power(a, 3))     # [8  27  64]
print(np.power(a, 0.5))   # [1.414 1.732 2.   ]  ← square root
print(np.power(2, a))     # [4 8 16]  ← broadcasting
```

---

### `np.sqrt()`
> Square root.

```python
a = np.array([4, 9, 16, 25])
print(np.sqrt(a))   # [2. 3. 4. 5.]

# Edge case: negative numbers
print(np.sqrt(-1))   # nan + warning
```

> ⚠️ **Exam Traps:**
> - Returns `float64` always
> - `np.sqrt(-1)` → `nan` (not an error, just NaN with RuntimeWarning!)

---

### `np.abs()`
> Absolute value.

```python
a = np.array([-3, -1, 0, 2, -5])
print(np.abs(a))   # [3 1 0 2 5]

# Works on complex numbers too!
b = np.array([3+4j])
print(np.abs(b))   # [5.]  ← magnitude = sqrt(3²+4²)
```

---

### `np.round()`, `np.floor()`, `np.ceil()`
> Rounding functions.

```python
a = np.array([1.2, 1.5, 1.7, 2.5, -1.5])

print(np.round(a))   # [1. 2. 2. 2. -2.]  ← Banker's rounding!
print(np.floor(a))   # [1. 1. 1. 2. -2.]  ← always toward -∞
print(np.ceil(a))    # [2. 2. 2. 3. -1.]  ← always toward +∞
```

> ⚠️ **Exam Traps:**
> - `np.round(0.5)` → `0.0`, `np.round(1.5)` → `2.0` — **Banker's rounding** (round to even!)
> - `np.floor(-1.5)` → `-2.0` (NOT `-1`! floor goes toward negative infinity)
> - All three return `float64`

---

### `np.exp()` and `np.log()`
> Exponential and natural log.

```python
a = np.array([0, 1, 2])
print(np.exp(a))    # [1.    2.718 7.389]  ← e^x

b = np.array([1, np.e, np.e**2])
print(np.log(b))    # [0. 1. 2.]  ← ln(x)

# Log of 0:
print(np.log(0))    # -inf  (not an error!)
print(np.log(-1))   # nan + warning
```

> ⚠️ **Exam Traps:**
> - `np.log` is **natural log** (base e), NOT log base 10!
> - `np.log10()` for base 10, `np.log2()` for base 2
> - `np.log(0)` → `-inf`, `np.log(-1)` → `nan`

---

### `np.dot()`
> Dot product / matrix multiplication.

```python
# 1D: dot product (scalar)
a = np.array([1,2,3])
b = np.array([4,5,6])
print(np.dot(a, b))   # 32  (= 1*4 + 2*5 + 3*6)

# 2D: matrix multiplication
A = np.array([[1,2],[3,4]])
B = np.array([[5,6],[7,8]])
print(np.dot(A, B))
# [[19 22]
#  [43 50]]
```

> ⚠️ **Exam Traps:**
> - 1D dot → scalar; 2D dot → matrix product (not element-wise!)
> - Shape rule for 2D: `(m,n) · (n,p) → (m,p)` — inner dims must match
> - `np.dot(A, B) ≠ A * B` — `*` is element-wise, `dot` is matrix product

---

## 📊 STATS

---

### `np.mean()`, `np.median()`, `np.std()`, `np.var()`

```python
a = np.array([[1,2,3],[4,5,6]])

print(np.mean(a))          # 3.5  (all elements)
print(np.mean(a, axis=0))  # [2.5 3.5 4.5]  (column means)
print(np.mean(a, axis=1))  # [2.  5. ]  (row means)

print(np.std(a))    # 1.707...  population std (ddof=0 by default!)
print(np.var(a))    # 2.916...
```

> ⚠️ **Exam Traps:**
> - Default `std` uses `ddof=0` (population), not `ddof=1` (sample)!
> - `np.std([2,4,4,4,5,5,7,9])` → `2.0` (population std)
> - `axis=0` collapses rows (result has shape of one row), `axis=1` collapses columns

---

### `np.sum()`, `np.min()`, `np.max()`

```python
a = np.array([[1,2,3],[4,5,6]])

print(np.sum(a))           # 21
print(np.sum(a, axis=0))   # [5 7 9]  (sum each column)
print(np.sum(a, axis=1))   # [6 15]   (sum each row)

print(np.min(a, axis=1))   # [1 4]   (min of each row)
print(np.max(a, axis=0))   # [4 5 6] (max of each column)
```

---

### `np.argmin()`, `np.argmax()`
> Return the **index** of min/max.

```python
a = np.array([3, 1, 4, 1, 5, 9, 2, 6])
print(np.argmax(a))   # 5  (index of 9)
print(np.argmin(a))   # 1  (index of first 1)

b = np.array([[1,2],[4,3]])
print(np.argmax(b, axis=0))  # [1 1]  ← index of max in each column
print(np.argmax(b, axis=1))  # [1 0]  ← index of max in each row
```

> ⚠️ **Exam Traps:**
> - When there are **ties**, `argmin`/`argmax` return the **first** occurrence
> - Without axis, returns flat index of the whole array

---

### `np.percentile()`

```python
a = np.array([1,2,3,4,5,6,7,8,9,10])
print(np.percentile(a, 50))   # 5.5  ← median
print(np.percentile(a, 25))   # 3.25
print(np.percentile(a, 75))   # 7.75
```

> ⚠️ **Exam Traps:**
> - `np.percentile(a, 50) == np.median(a)` → True
> - Argument is 0-100, not 0-1

---

### `np.cumsum()`, `np.cumprod()`
> Cumulative sum/product.

```python
a = np.array([1, 2, 3, 4])
print(np.cumsum(a))    # [1  3  6 10]
print(np.cumprod(a))   # [1  2  6 24]

b = np.array([[1,2],[3,4]])
print(np.cumsum(b, axis=0))
# [[1 2]
#  [4 6]]  ← cumulative down columns
```

---

### `np.corrcoef()`, `np.cov()`
> Correlation matrix and covariance matrix.

```python
x = np.array([1,2,3,4,5])
y = np.array([2,4,5,4,5])

print(np.corrcoef(x, y))
# [[1.    0.927]
#  [0.927 1.   ]]  ← diagonal is always 1

print(np.cov(x, y))
# [[2.5  2.  ]
#  [2.   1.7 ]]
```

> ⚠️ **Exam Traps:**
> - `corrcoef` returns a **matrix**, not a single number
> - The correlation between x and y is `result[0,1]` or `result[1,0]`
> - `np.cov` uses `ddof=1` (sample covariance) by default

---

## 🔎 SEARCHING

---

### `np.where()`
> Conditional selection: `np.where(condition, x, y)`

```python
a = np.array([1, -2, 3, -4, 5])

# Example 1 — Replace negatives with 0
b = np.where(a > 0, a, 0)
print(b)   # [1 0 3 0 5]

# Example 2 — Binary labels
c = np.where(a > 0, "pos", "neg")
print(c)   # ['pos' 'neg' 'pos' 'neg' 'pos']

# Example 3 — Get indices only (one argument)
idx = np.where(a > 0)
print(idx)   # (array([0, 2, 4]),)
```

> ⚠️ **Exam Traps:**
> - `np.where(condition)` with ONE arg → returns **tuple of indices** (not values!)
> - `np.where(condition, x, y)` with THREE args → returns values
> - Result is a tuple even for 1D: `(array([...]),)`

---

### `np.nonzero()`
> Returns indices of non-zero elements.

```python
a = np.array([0, 1, 0, 3, 0, 5])
print(np.nonzero(a))   # (array([1, 3, 5]),)

b = np.array([[0,1],[2,0]])
print(np.nonzero(b))   # (array([0,1]), array([1,0]))  ← row, col indices
```

> ⚠️ **Exam Traps:**
> - Returns a **tuple** of arrays (one per dimension)
> - For 2D: first array = row indices, second = column indices

---

### `np.searchsorted()`
> Find index where a value should be inserted to keep array sorted.

```python
a = np.array([1, 3, 5, 7, 9])
print(np.searchsorted(a, 4))    # 2 (insert 4 at index 2)
print(np.searchsorted(a, 5))    # 2 (default: 'left')
print(np.searchsorted(a, 5, side='right'))  # 3
```

> ⚠️ **Exam Traps:**
> - Array must be **sorted** for correct results
> - `side='left'` (default): finds leftmost valid position; `side='right'` finds rightmost

---

## 🔀 SORTING

---

### `np.sort()`
> Return a **sorted copy** of array.

```python
a = np.array([3, 1, 4, 1, 5, 9, 2])
print(np.sort(a))   # [1 1 2 3 4 5 9]  ← original unchanged!

b = np.array([[3,1],[2,4]])
print(np.sort(b, axis=0))   # sort each column: [[2,1],[3,4]]
print(np.sort(b, axis=1))   # sort each row: [[1,3],[2,4]]
```

> ⚠️ **Exam Traps:**
> - `np.sort(a)` returns a **copy** — original `a` is unchanged
> - `a.sort()` modifies **in-place** — original changes!

---

### `np.argsort()`
> Returns indices that would sort the array.

```python
a = np.array([30, 10, 20])
idx = np.argsort(a)
print(idx)       # [1 2 0]  (index of smallest to largest)
print(a[idx])    # [10 20 30]  ← sorted via fancy indexing
```

> ⚠️ **Exam Traps:**
> - Returns **indices**, not sorted values
> - Useful for sorting one array by another array's order

---

### `np.lexsort()`
> Sort by multiple keys (last key = primary sort).

```python
# Sort by last name, then first name
last  = np.array(['Smith', 'Jones', 'Smith'])
first = np.array(['Bob',   'Alice', 'Alice'])

idx = np.lexsort((first, last))  # last is primary key!
print(idx)   # [2 1 0]  ← Alice Smith, Alice Jones, Bob Smith... wait:
# Sorted: Alice Smith(2), Alice Jones... 
# Actually: Jones Alice(1), Smith Alice(2), Smith Bob(0)
```

> ⚠️ **Exam Traps:**
> - Keys are applied **last to first** — the **last** argument is the **primary** sort key!
> - `np.lexsort((secondary, primary))` — reversed from intuition

---

## 🔗 JOIN & SPLIT

---

### `np.concatenate()`
> Join arrays along an **existing** axis.

```python
a = np.array([[1,2],[3,4]])
b = np.array([[5,6]])

# axis=0: stack vertically (add rows)
print(np.concatenate([a, b], axis=0))
# [[1 2]
#  [3 4]
#  [5 6]]

# axis=1: stack horizontally (add columns)
c = np.array([[7],[8]])
print(np.concatenate([a, c], axis=1))
# [[1 2 7]
#  [3 4 8]]
```

> ⚠️ **Exam Traps:**
> - Shapes must be compatible along all axes EXCEPT the concatenation axis
> - `axis=0`: number of **columns** must match; `axis=1`: number of **rows** must match

---

### `np.stack()` vs `np.vstack()` vs `np.hstack()`

```python
a = np.array([1,2,3])
b = np.array([4,5,6])

print(np.stack([a,b]))      # shape (2,3) ← NEW axis created
# [[1 2 3]
#  [4 5 6]]

print(np.vstack([a,b]))     # shape (2,3) ← vertical (axis=0)
# [[1 2 3]
#  [4 5 6]]

print(np.hstack([a,b]))     # shape (6,) ← horizontal (axis=1 for 2D, concatenates for 1D)
# [1 2 3 4 5 6]
```

> ⚠️ **Exam Traps:**
> - `np.stack` creates a **new axis**; `np.concatenate` does NOT
> - For 1D arrays: `hstack` concatenates → `(6,)`; `vstack` stacks → `(2,3)`
> - For 2D: `vstack` adds rows, `hstack` adds columns

---

### `np.split()`, `np.array_split()`

```python
a = np.arange(12)

# Equal split into 3
parts = np.split(a, 3)
print(parts)   # [array([0,1,2,3]), array([4,5,6,7]), array([8,9,10,11])]

# Split at indices
parts2 = np.split(a, [3, 7])
print(parts2)  # [array([0,1,2]), array([3,4,5,6]), array([7,8,9,10,11])]

# Unequal split (doesn't raise error)
parts3 = np.array_split(a, 5)  # 12/5 not exact → some have extra element
```

> ⚠️ **Exam Traps:**
> - `np.split(a, 3)` fails if array can't be equally divided — use `array_split` for unequal
> - When second arg is a list, it's **split positions**, not number of pieces

---

### `np.tile()` vs `np.repeat()`

```python
a = np.array([1, 2, 3])

print(np.tile(a, 3))      # [1 2 3 1 2 3 1 2 3]  ← repeats the whole array
print(np.repeat(a, 3))    # [1 1 1 2 2 2 3 3 3]  ← repeats each element
```

> ⚠️ **Exam Traps:**
> - `tile` = copy the entire array N times
> - `repeat` = repeat each individual element N times
> - Completely different results — very common exam trap!

---

### `np.delete()`, `np.insert()`, `np.append()`

```python
a = np.array([10, 20, 30, 40, 50])

print(np.delete(a, 2))         # [10 20 40 50]  ← removes index 2
print(np.insert(a, 2, 99))     # [10 20 99 30 40 50]  ← insert 99 at index 2
print(np.append(a, [60, 70]))  # [10 20 30 40 50 60 70]
```

> ⚠️ **Exam Traps:**
> - All three return **copies** — original array is unchanged!
> - `np.append` is slow for repeated use — better to collect and `concatenate` once

---

## ✅ LOGIC

---

### `np.all()` and `np.any()`

```python
a = np.array([True, True, False])
print(np.all(a))   # False  (not ALL are true)
print(np.any(a))   # True   (at least one is true)

b = np.array([[1,2],[0,4]])
print(np.all(b > 0))           # False  (0 fails)
print(np.all(b > 0, axis=0))   # [False  True]  (check each column)
print(np.any(b > 0, axis=1))   # [True   True]  (check each row)
```

> ⚠️ **Exam Traps:**
> - `np.all([])` → `True` (vacuously true — empty array)
> - `np.any([])` → `False`

---

### `np.logical_and()`, `np.logical_or()`, `np.logical_not()`

```python
a = np.array([True, True, False, False])
b = np.array([True, False, True, False])

print(np.logical_and(a, b))  # [T F F F]
print(np.logical_or(a, b))   # [T T T F]
print(np.logical_not(a))     # [F F T T]
```

> ⚠️ **Exam Traps:**
> - Use `np.logical_and` for arrays — Python's `and` doesn't work element-wise!
> - `&` works too but has operator precedence issues: write `(a>1) & (a<5)` with parentheses!

---

### `np.isnan()`, `np.isinf()`, `np.isclose()`

```python
a = np.array([1.0, np.nan, np.inf, -np.inf])

print(np.isnan(a))    # [F  T  F  F]
print(np.isinf(a))    # [F  F  T  T]

# isclose: safer float comparison
print(np.isclose(0.1 + 0.2, 0.3))   # True  ← float precision handled!
print(0.1 + 0.2 == 0.3)             # False ← direct comparison fails!
```

> ⚠️ **Exam Traps:**
> - `nan == nan` is `False` in Python/NumPy — use `np.isnan()` instead
> - `np.inf > 1000000` is `True` (inf is greater than any number)
> - Always use `np.isclose()` for floating point comparisons, never `==`

---

## 🔢 LINEAR ALGEBRA

---

### `np.matmul()`
> Matrix multiplication (preferred over `np.dot` for 2D+).

```python
A = np.array([[1,2],[3,4]])
B = np.array([[5,6],[7,8]])

C = np.matmul(A, B)
# [[19 22]
#  [43 50]]

# Equivalent:
C = A @ B   # @ operator is cleanest way!
```

> ⚠️ **Exam Traps:**
> - `matmul` does NOT support scalar multiplication (use `np.dot` or `*` for that)
> - `A @ B` ≠ `A * B` (@ is matrix product; * is element-wise)

---

### `np.linalg.inv()`, `np.linalg.det()`

```python
A = np.array([[1,2],[3,4]])

inv_A = np.linalg.inv(A)
print(inv_A)
# [[-2.   1. ]
#  [ 1.5 -0.5]]

# Verify: A @ inv(A) = Identity
print(np.round(A @ inv_A))  # [[1. 0.] [0. 1.]]

print(np.linalg.det(A))     # -2.0
```

> ⚠️ **Exam Traps:**
> - Singular matrix (det=0) → `linalg.inv` raises `LinAlgError`
> - Results have floating point errors — use `np.round` to verify

---

### `np.linalg.eig()`
> Eigenvalues and eigenvectors.

```python
A = np.array([[4, 1],[2, 3]])
eigenvalues, eigenvectors = np.linalg.eig(A)
print(eigenvalues)    # [5. 2.]
print(eigenvectors)   # columns are eigenvectors!
```

> ⚠️ **Exam Traps:**
> - Returns **(values, vectors)** — unpack into two variables
> - Eigenvectors are the **columns** of the returned matrix, not the rows

---

### `np.linalg.norm()`
> Compute the norm (magnitude) of a vector or matrix.

```python
a = np.array([3, 4])
print(np.linalg.norm(a))      # 5.0  (L2/Euclidean by default)
print(np.linalg.norm(a, 1))   # 7.0  (L1 norm = sum of abs values)
print(np.linalg.norm(a, np.inf))  # 4.0  (max absolute value)
```

---

### `np.diag()`
> Extract diagonal or construct diagonal matrix.

```python
A = np.array([[1,2,3],[4,5,6],[7,8,9]])

# Extract main diagonal
print(np.diag(A))         # [1 5 9]

# Build diagonal matrix from 1D array
v = np.array([1, 2, 3])
print(np.diag(v))
# [[1 0 0]
#  [0 2 0]
#  [0 0 3]]
```

> ⚠️ **Exam Traps:**
> - `np.diag(2D)` → extracts diagonal (1D output)
> - `np.diag(1D)` → creates diagonal matrix (2D output)
> - `np.diagonal(A)` only extracts, never constructs

---

## 🎲 RANDOM

---

### `np.random.rand()` vs `np.random.randn()`

```python
# rand: Uniform distribution [0, 1)
a = np.random.rand(3, 2)   # shape (3,2), values between 0 and 1

# randn: Standard Normal (mean=0, std=1)
b = np.random.randn(3, 2)  # values centered around 0, can be negative!
```

> ⚠️ **Exam Traps:**
> - `rand` → uniform [0,1); `randn` → normal, can be NEGATIVE
> - `rand(3,2)` takes separate args; `np.random.random((3,2))` takes a tuple

---

### `np.random.randint()`

```python
# randint(low, high) → high is EXCLUSIVE
a = np.random.randint(1, 7)      # single die roll: 1-6
b = np.random.randint(0, 2, 5)   # 5 coin flips: 0 or 1
c = np.random.randint(1, 10, (3,3))  # 3x3 matrix
```

> ⚠️ **Exam Traps:**
> - High is **exclusive**: `randint(1,7)` → 1 to 6 (never 7!)
> - `randint(5)` → random int from 0 to 4

---

### `np.random.choice()`

```python
a = np.array([10, 20, 30, 40, 50])

# Random pick
print(np.random.choice(a))         # single random element

# Multiple picks (with replacement by default)
print(np.random.choice(a, 3))      # 3 picks, can repeat

# Without replacement
print(np.random.choice(a, 3, replace=False))  # no repeats

# With probabilities
print(np.random.choice(a, 3, p=[0.1,0.1,0.6,0.1,0.1]))  # 30 is most likely
```

> ⚠️ **Exam Traps:**
> - Default is `replace=True` (can repeat)
> - `replace=False` requires requested size ≤ array size
> - Probabilities in `p` must sum to **1.0**

---

### `np.random.seed()`
> Set random seed for reproducibility.

```python
np.random.seed(42)
a = np.random.rand(3)
print(a)   # [0.374 0.951 0.732]  ← always same with seed 42

np.random.seed(42)
b = np.random.rand(3)
print(b)   # [0.374 0.951 0.732]  ← identical!
```

> ⚠️ **Exam Traps:**
> - Must set seed **before each** block you want to reproduce
> - Different libraries (`random`, `torch`) have their own seeds — setting np seed doesn't affect them

---

### `np.random.normal()` and `np.random.uniform()`

```python
# normal(mean, std, size)
a = np.random.normal(0, 1, 1000)      # standard normal
b = np.random.normal(100, 15, 500)    # IQ-like distribution

# uniform(low, high, size)  — high is INCLUSIVE here (unlike randint)
c = np.random.uniform(0, 1, 5)    # same as rand(5)
d = np.random.uniform(-1, 1, 5)   # values in [-1, 1]
```

> ⚠️ **Exam Traps:**
> - `normal(mean, std)` — second arg is **std deviation**, NOT variance
> - `uniform(low, high)` — both endpoints technically possible (unlike `randint` where high is exclusive)

---

## 🧠 Quick Reference Cheat Sheet

| Trap | Correct Understanding |
|------|----------------------|
| `np.zeros(5)` dtype | `float64` by default, not int |
| `np.linspace(0,1,5)` | 5 **points**, stop is **included** |
| `np.arange(0,5)` | stop is **excluded** → `[0,1,2,3,4]` |
| Transpose 1D | `.T` does nothing to 1D arrays! |
| `flatten` vs `ravel` | `flatten` = copy, `ravel` = view |
| `tile` vs `repeat` | `tile` repeats array, `repeat` repeats elements |
| `np.sort(a)` | returns copy; `a.sort()` is in-place |
| `np.dot` vs `*` | `dot` = matrix product, `*` = element-wise |
| `nan == nan` | Always `False`! Use `np.isnan()` |
| `np.round(0.5)` | `0.0` (Banker's rounding!) |
| `np.floor(-1.5)` | `-2.0` (toward negative infinity) |
| `np.std` default | Population std (`ddof=0`), not sample |
| `np.where(cond)` 1 arg | Returns **indices**, not values |
| `np.lexsort` key order | **Last** argument = **primary** sort key |
| `np.random.randint(1,7)` | 7 is **excluded** → max is 6 |
| `argmax` with ties | Returns **first** occurrence index |
| `np.linalg.eig` | Returns `(values, vectors)` — vectors are **columns** |
| `np.diag(2D)` vs `np.diag(1D)` | 2D → extracts diagonal; 1D → builds matrix |

---

> 💡 **Pro tip:** When in doubt between two functions, test with a tiny array and print both shape and values!
aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa

aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa


aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa

# 🐼 Pandas Complete Cheat Sheet — Exam Edition

> **Beginner-friendly syntax + Exam-style examples + Common mistakes to avoid**

---

## 📌 Table of Contents
- [📥 IO — Reading & Writing Data](#-io--reading--writing-data)
- [🔍 CORE — DataFrame Basics](#-core--dataframe-basics)
- [📊 EXPLORATION — Stats & Analysis](#-exploration--stats--analysis)
- [🎯 SELECTION — Filtering & Indexing](#-selection--filtering--indexing)
- [🧹 CLEANING — Handling Messy Data](#-cleaning--handling-messy-data)
- [🔄 TRANSFORMATION — Reshaping Data](#-transformation--reshaping-data)
- [📦 AGGREGATION — Grouping & Windows](#-aggregation--grouping--windows)
- [🔗 MERGING — Combining DataFrames](#-merging--combining-dataframes)
- [⏰ TIME — Date & Time Operations](#-time--date--time-operations)

---

## 📥 IO — Reading & Writing Data

### `pd.read_csv()` — Read a CSV file

```python
import pandas as pd

df = pd.read_csv('data.csv')
df = pd.read_csv('data.csv', index_col='ID')        # set a column as index
df = pd.read_csv('data.csv', usecols=['A', 'B'])    # load only specific columns
```

**📝 Exam Examples:**
```python
# Q: Load only the 'Name' and 'Score' columns from students.csv
df = pd.read_csv('students.csv', usecols=['Name', 'Score'])

# Q: Load CSV where first column is the index
df = pd.read_csv('data.csv', index_col=0)

# Q: Load CSV with missing values represented as 'N/A'
df = pd.read_csv('data.csv', na_values=['N/A', 'missing'])
```

**⚠️ Common Mistakes:**
```python
# ❌ Wrong: forgetting index_col makes pandas add its own numeric index
df = pd.read_csv('data.csv')  # now has extra 0,1,2... index + original ID column

# ✅ Right: if CSV already has an ID column meant to be index
df = pd.read_csv('data.csv', index_col='ID')
```

---

### `pd.read_json()` — Read a JSON file

```python
df = pd.read_json('data.json')
df = pd.read_json('data.json', orient='records')    # list of {col:val} dicts
df = pd.read_json('data.json', orient='index')      # dict of {index: {col:val}}
```

**📝 Exam Examples:**
```python
# Q: Read JSON where data is a list of records
df = pd.read_json('students.json', orient='records')

# Q: Read JSON from a URL string
df = pd.read_json('https://example.com/data.json')
```

**⚠️ Common Mistakes:**
```python
# ❌ Wrong orient causes column/row mismatch
df = pd.read_json('data.json', orient='columns')   # may transpose your data

# ✅ Always verify shape after reading: df.shape
```

---

### `pd.read_sql()` — Read SQL query

```python
import sqlite3
conn = sqlite3.connect('mydb.db')

df = pd.read_sql('SELECT * FROM students', conn)
df = pd.read_sql('SELECT name, score FROM students WHERE score > 80', conn)
```

**📝 Exam Examples:**
```python
# Q: Fetch all rows from 'employees' table
df = pd.read_sql('SELECT * FROM employees', conn)

# Q: Fetch with condition
df = pd.read_sql('SELECT * FROM sales WHERE region = "North"', conn)
```

**⚠️ Common Mistakes:**
```python
# ❌ Forgetting to pass the connection object
df = pd.read_sql('SELECT * FROM table')  # TypeError!

# ✅ Always pass the connection as second argument
df = pd.read_sql('SELECT * FROM table', conn)
```

---

### `pd.read_excel()` — Read Excel file

```python
df = pd.read_excel('data.xlsx')
df = pd.read_excel('data.xlsx', sheet_name='Sheet2')    # specific sheet
df = pd.read_excel('data.xlsx', sheet_name=0)           # first sheet by index
```

**📝 Exam Examples:**
```python
# Q: Read second sheet named 'Sales' from workbook
df = pd.read_excel('report.xlsx', sheet_name='Sales')

# Q: Read all sheets into a dict
all_sheets = pd.read_excel('report.xlsx', sheet_name=None)
```

**⚠️ Common Mistakes:**
```python
# ❌ Wrong: sheet_name is case-sensitive!
df = pd.read_excel('data.xlsx', sheet_name='sheet1')   # KeyError if it's 'Sheet1'

# ❌ Missing library
# Must install: pip install openpyxl
```

---

### `pd.read_xml()` — Read XML document

```python
df = pd.read_xml('data.xml')
df = pd.read_xml('data.xml', xpath='.//student')    # using XPath to select nodes
```

**📝 Exam Examples:**
```python
# Q: Read XML and select specific tags
df = pd.read_xml('students.xml', xpath='.//record')
```

---

### `pd.read_html()` — Read HTML tables

```python
tables = pd.read_html('https://example.com/table.html')   # returns a LIST
df = tables[0]    # first table on the page
```

**📝 Exam Examples:**
```python
# Q: Read the second table from a webpage
tables = pd.read_html('https://site.com/stats')
df = tables[1]   # index 1 = second table
```

**⚠️ Common Mistakes:**
```python
# ❌ Treating result as a single DataFrame
df = pd.read_html('url')           # WRONG — this is a list!
df = pd.read_html('url')[0]        # ✅ Always index into it
```

---

### `to_csv()` — Write to CSV

```python
df.to_csv('output.csv')
df.to_csv('output.csv', index=False)         # don't write index
df.to_csv('output.csv', columns=['A', 'B'])  # only specific columns
```

**📝 Exam Examples:**
```python
# Q: Save DataFrame without the default numeric index
df.to_csv('result.csv', index=False)

# Q: Save only 'Name' and 'Score' columns
df.to_csv('result.csv', columns=['Name', 'Score'], index=False)
```

**⚠️ Common Mistakes:**
```python
# ❌ Forgetting index=False — creates ugly unnamed column when re-read
df.to_csv('out.csv')               # saves index as extra column
df2 = pd.read_csv('out.csv')       # now has 'Unnamed: 0' column!

# ✅ Use index=False unless you need the index
df.to_csv('out.csv', index=False)
```

---

### `to_excel()` — Write to Excel

```python
df.to_excel('output.xlsx', index=False)
df.to_excel('output.xlsx', sheet_name='Results', index=False)
```

---

### `to_json()` — Write to JSON

```python
df.to_json('output.json')
df.to_json('output.json', orient='records')    # list of dicts format
```

---

### `to_sql()` — Write to SQL

```python
df.to_sql('table_name', conn, if_exists='replace', index=False)
# if_exists options: 'fail', 'replace', 'append'
```

**⚠️ Common Mistakes:**
```python
# ❌ Default if_exists='fail' throws error if table exists
df.to_sql('data', conn)                              # ValueError if table exists!

# ✅ Use replace or append
df.to_sql('data', conn, if_exists='replace')
```

---

### `to_parquet()` — Write to Parquet

```python
df.to_parquet('data.parquet')
df.to_parquet('data.parquet', compression='snappy')   # compressed
```

---

### `to_pickle()` — Pickle object

```python
df.to_pickle('data.pkl')
df2 = pd.read_pickle('data.pkl')    # read it back
```

---

## 🔍 CORE — DataFrame Basics

### `head()` / `tail()` — First/Last n rows

```python
df.head()       # first 5 rows (default)
df.head(10)     # first 10 rows
df.tail()       # last 5 rows
df.tail(3)      # last 3 rows
```

**📝 Exam Examples:**
```python
# Q: Display top 3 records
df.head(3)

# Q: Get last 2 entries to check recent data
df.tail(2)
```

**⚠️ Common Mistakes:**
```python
# ❌ head returns a copy — it doesn't modify df!
df.head(3)           # df is still full size
top3 = df.head(3)    # ✅ store if you need it
```

---

### `info()` — DataFrame summary

```python
df.info()
df.info(verbose=True)          # full column info
df.info(memory_usage='deep')   # accurate memory
```

**📝 Exam Examples:**
```python
# Q: Check how many non-null values each column has
df.info()   # shows Non-Null Count per column

# Q: Find which columns have missing values
df.info()   # columns with count < total rows have NAs
```

---

### `describe()` — Statistics summary

```python
df.describe()                        # numeric columns only
df.describe(include='all')           # all columns including object
df.describe(include=['object'])      # only string/categorical
```

**📝 Exam Examples:**
```python
# Q: Get mean, std, min, max for all numeric columns
df.describe()

# Q: Include string columns in summary
df.describe(include='all')

# Q: What is the 25th percentile of 'Score'?
df.describe()   # look at '25%' row in Score column
```

**⚠️ Common Mistakes:**
```python
# ❌ describe() skips non-numeric by default
df.describe()['Name']    # KeyError — 'Name' is string, not included!

# ✅ Use include='all'
df.describe(include='all')['Name']
```

---

### `shape` — Dimensions

```python
df.shape          # (rows, columns) as tuple
df.shape[0]       # number of rows
df.shape[1]       # number of columns
```

**📝 Exam Examples:**
```python
# Q: How many rows and columns?
rows, cols = df.shape

# Q: Count only rows
n = df.shape[0]
```

**⚠️ Common Mistakes:**
```python
# ❌ shape is an attribute, not a method — no parentheses!
df.shape()    # TypeError!
df.shape      # ✅
```

---

### `dtypes` — Data types

```python
df.dtypes            # dtype per column
df['col'].dtype      # dtype of one column
```

**📝 Exam Examples:**
```python
# Q: Check if 'Date' column is datetime type
df.dtypes['Date']   # may show object — needs conversion!

# Q: List all columns and their types
print(df.dtypes)
```

**⚠️ Common Mistakes:**
```python
# ❌ dtypes is attribute, not method
df.dtypes()   # TypeError!

# ❌ Assuming numbers read from CSV are int/float
# CSV numbers often load as 'object' if column has mixed content
```

---

### `columns` — Column labels

```python
df.columns                          # Index of column names
df.columns.tolist()                 # as Python list
df.columns = ['A', 'B', 'C']       # rename all columns
```

**📝 Exam Examples:**
```python
# Q: Get list of all column names
cols = df.columns.tolist()

# Q: Rename all columns at once
df.columns = ['id', 'name', 'score']
```

---

### `index` — Index labels

```python
df.index                   # Index object
df.index.tolist()          # as list
```

---

### `values` — Numpy array

```python
arr = df.values           # returns numpy ndarray
arr = df.to_numpy()       # preferred modern way
```

**⚠️ Common Mistakes:**
```python
# ❌ values loses column names — be careful comparing with df
arr = df.values   # just raw numbers, no column context
```

---

### `ndim` — Number of dimensions

```python
df.ndim     # always 2 for DataFrame
s.ndim      # always 1 for Series
```

---

### `size` — Total elements

```python
df.size     # rows × columns (total cells, including NaN)
```

**⚠️ Common Mistakes:**
```python
# ❌ size ≠ number of rows!
df.size      # total CELLS = rows × columns
df.shape[0]  # ✅ number of rows only
```

---

### `empty` — Is DataFrame empty?

```python
df.empty    # True if no elements
```

**📝 Exam Examples:**
```python
# Q: Check if filtered result has any rows
result = df[df['score'] > 100]
if result.empty:
    print("No students scored above 100")
```

---

### `memory_usage()` — Memory usage

```python
df.memory_usage()              # per column in bytes
df.memory_usage(deep=True)     # accurate for object columns
df.memory_usage().sum()        # total memory
```

---

### `pd.DataFrame()` — Create DataFrame

```python
# From dict
df = pd.DataFrame({'Name': ['Alice', 'Bob'], 'Score': [85, 92]})

# From list of lists
df = pd.DataFrame([[1, 2], [3, 4]], columns=['A', 'B'])

# From list of dicts
df = pd.DataFrame([{'Name': 'Alice', 'Age': 20}, {'Name': 'Bob', 'Age': 22}])
```

**📝 Exam Examples:**
```python
# Q: Create a DataFrame with 3 students and their marks
df = pd.DataFrame({
    'Student': ['Alice', 'Bob', 'Charlie'],
    'Math': [90, 85, 78],
    'Science': [88, 92, 80]
})

# Q: Create from list of records
records = [('Alice', 90), ('Bob', 85)]
df = pd.DataFrame(records, columns=['Name', 'Score'])
```

**⚠️ Common Mistakes:**
```python
# ❌ Lists must be same length!
df = pd.DataFrame({'A': [1, 2, 3], 'B': [1, 2]})   # ValueError!

# ❌ Missing column names when creating from nested lists
df = pd.DataFrame([[1, 2], [3, 4]])   # columns become 0, 1 (integers)
```

---

### `pd.Series()` — Create Series

```python
s = pd.Series([10, 20, 30])
s = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
s = pd.Series({'x': 1, 'y': 2})
```

**📝 Exam Examples:**
```python
# Q: Create a Series of scores with student names as index
s = pd.Series([85, 92, 78], index=['Alice', 'Bob', 'Charlie'], name='Score')

# Access by label
s['Alice']    # 85
```

---

## 📊 EXPLORATION — Stats & Analysis

### `mean()` / `median()` / `mode()`

```python
df['Score'].mean()       # average
df['Score'].median()     # middle value
df['Score'].mode()       # most frequent (returns Series!)
df.mean()                # mean of all numeric columns
```

**📝 Exam Examples:**
```python
# Q: Find average score
avg = df['Score'].mean()

# Q: Find most common grade
most_common = df['Grade'].mode()[0]   # [0] to get the scalar value
```

**⚠️ Common Mistakes:**
```python
# ❌ mode() returns a Series, not a scalar!
val = df['col'].mode()      # Series: 0    value
val = df['col'].mode()[0]   # ✅ get actual value

# ❌ mean() ignores NaN by default (which is usually fine, but know it)
df['col'].mean()              # skips NaN
df['col'].mean(skipna=False)  # returns NaN if any NaN present
```

---

### `min()` / `max()`

```python
df['Score'].min()
df['Score'].max()
df[['Math', 'Science']].max()    # max per column
```

**📝 Exam Examples:**
```python
# Q: Find highest and lowest score
print(df['Score'].min(), df['Score'].max())

# Q: Find max in each subject
df[['Math', 'Science', 'English']].max()
```

---

### `sum()` / `count()`

```python
df['Score'].sum()       # sum of values
df['Score'].count()     # count of non-NA values
df.count()              # non-NA count per column
```

**⚠️ Common Mistakes:**
```python
# ❌ count() counts NON-NA values, not total rows!
df['col'].count()    # skips NaN
len(df)              # ✅ total rows including NaN rows
df.shape[0]          # ✅ same
```

---

### `std()` / `var()` / `sem()`

```python
df['Score'].std()    # standard deviation (ddof=1 by default)
df['Score'].var()    # variance
df['Score'].sem()    # standard error of mean
```

**⚠️ Common Mistakes:**
```python
# ❌ pandas uses ddof=1 (sample std), numpy uses ddof=0 (population std)
df['Score'].std()         # sample std (n-1)
np.std(df['Score'])       # population std (n) — different answer!
df['Score'].std(ddof=0)   # ✅ match numpy if needed
```

---

### `skew()` / `kurt()`

```python
df['Score'].skew()    # skewness (0=normal, +ve=right skew)
df['Score'].kurt()    # kurtosis (0=normal for excess kurtosis)
```

---

### `quantile()`

```python
df['Score'].quantile(0.25)    # Q1
df['Score'].quantile(0.75)    # Q3
df['Score'].quantile([0.25, 0.5, 0.75])    # multiple at once
```

**📝 Exam Examples:**
```python
# Q: Find IQR (Interquartile Range)
Q1 = df['Score'].quantile(0.25)
Q3 = df['Score'].quantile(0.75)
IQR = Q3 - Q1
```

---

### `cov()` / `corr()`

```python
df.cov()                   # covariance matrix
df.corr()                  # correlation matrix (Pearson default)
df['A'].corr(df['B'])      # correlation between two columns
df.corr(method='spearman') # Spearman correlation
```

**📝 Exam Examples:**
```python
# Q: Find correlation between Math and Science scores
corr_val = df['Math'].corr(df['Science'])

# Q: Which columns are most correlated?
df.corr()   # examine the matrix — values close to 1 or -1
```

**⚠️ Common Mistakes:**
```python
# ❌ Correlation matrix diagonal is always 1 (self-correlation)
# ❌ corr() only works on numeric columns
df[['Name', 'Score']].corr()   # 'Name' is dropped automatically
```

---

### `value_counts()`

```python
df['Grade'].value_counts()              # count each unique value, sorted
df['Grade'].value_counts(normalize=True) # as proportions (0 to 1)
df['Grade'].value_counts(dropna=False)  # include NaN count
```

**📝 Exam Examples:**
```python
# Q: How many students got each grade?
df['Grade'].value_counts()

# Q: What percentage of students passed (grade='A' or 'B')?
pct = df['Grade'].value_counts(normalize=True) * 100
```

**⚠️ Common Mistakes:**
```python
# ❌ value_counts() on DataFrame doesn't work directly
df.value_counts()           # works but counts full row combinations
df['col'].value_counts()    # ✅ use on a single column (Series)
```

---

### `nunique()` / `unique()`

```python
df['City'].nunique()    # number of unique values (scalar)
df['City'].unique()     # array of unique values
df.nunique()            # unique count per column
```

**📝 Exam Examples:**
```python
# Q: How many different cities are in the dataset?
df['City'].nunique()

# Q: List all unique departments
df['Dept'].unique()
```

**⚠️ Common Mistakes:**
```python
# ❌ unique() returns array, not list
vals = df['col'].unique()    # numpy array
vals = df['col'].unique().tolist()  # ✅ convert if needed

# ❌ nunique() vs unique() confusion in exam!
df['col'].nunique()   # → scalar count (e.g., 5)
df['col'].unique()    # → array of values (e.g., ['A','B','C'...])
```

---

### `nlargest()` / `nsmallest()`

```python
df.nlargest(3, 'Score')      # top 3 rows by Score
df.nsmallest(5, 'Salary')    # bottom 5 rows by Salary
df['Score'].nlargest(3)      # on a Series
```

**📝 Exam Examples:**
```python
# Q: Get top 5 students by score
top5 = df.nlargest(5, 'Score')

# Q: Find 3 cheapest products
cheap = df.nsmallest(3, 'Price')
```

**⚠️ Common Mistakes:**
```python
# ❌ nlargest on Series vs DataFrame — different syntax
df['Score'].nlargest(3)          # Series method — returns Series
df.nlargest(3, 'Score')          # DataFrame method — returns full rows ✅
```

---

### `idxmax()` / `idxmin()`

```python
df['Score'].idxmax()    # INDEX label of maximum value
df['Score'].idxmin()    # INDEX label of minimum value
```

**📝 Exam Examples:**
```python
# Q: Which student has the highest score?
idx = df['Score'].idxmax()
df.loc[idx, 'Name']    # use the index to get name

# Q: Find row index of lowest price
df['Price'].idxmin()   # returns the index label
```

**⚠️ Common Mistakes:**
```python
# ❌ idxmax() returns the INDEX, not the value!
df['Score'].idxmax()          # e.g., returns 4 (row label)
df['Score'].max()             # returns actual max value

# ❌ If multiple maxes exist, idxmax() returns the FIRST one only
```

---

## 🎯 SELECTION — Filtering & Indexing

### `loc[]` — Label-based selection

```python
df.loc[0]                      # row with index label 0
df.loc[0, 'Name']              # specific cell
df.loc[0:3, 'Name':'Score']    # slice (INCLUSIVE on both ends!)
df.loc[df['Score'] > 80]       # boolean filtering
```

**📝 Exam Examples:**
```python
# Q: Select rows 2 to 5 and columns 'Name', 'Score'
df.loc[2:5, ['Name', 'Score']]

# Q: Get all students with score above 80
df.loc[df['Score'] > 80]

# Q: Update a specific cell
df.loc[0, 'Score'] = 95
```

**⚠️ Common Mistakes:**
```python
# ❌ loc with slicing is INCLUSIVE on both ends (unlike Python!)
df.loc[0:3]   # includes rows 0, 1, 2, AND 3!
df.iloc[0:3]  # includes only 0, 1, 2 (exclusive end like Python)

# ❌ loc uses LABELS, not positions — dangerous when index is not 0,1,2...
df.index = ['a','b','c']
df.loc[0]     # KeyError! Label 0 doesn't exist
df.loc['a']   # ✅
```

---

### `iloc[]` — Position-based selection

```python
df.iloc[0]              # first row (by position)
df.iloc[-1]             # last row
df.iloc[0, 1]           # row 0, column 1
df.iloc[0:3, 0:2]       # first 3 rows, first 2 cols (exclusive end)
df.iloc[[0, 2, 4]]      # specific rows by position
```

**📝 Exam Examples:**
```python
# Q: Select first 3 rows and first 2 columns
df.iloc[:3, :2]

# Q: Get last row
df.iloc[-1]

# Q: Get every other row
df.iloc[::2]
```

**⚠️ Common Mistakes:**
```python
# ❌ iloc slicing is exclusive on the end (like Python lists)
df.iloc[0:3]     # rows 0, 1, 2 only (NOT 3)
df.loc[0:3]      # rows 0, 1, 2, 3 (INCLUSIVE)

# ❌ iloc doesn't accept column names — positions only!
df.iloc[0, 'Name']   # TypeError!
df.iloc[0, 0]        # ✅ use position number
```

---

### `at[]` / `iat[]` — Single value access

```python
df.at[2, 'Name']     # by label — fast scalar access
df.iat[2, 0]         # by position — fast scalar access
```

**📝 Exam Examples:**
```python
# Q: Get value at row index 3, column 'Score' (fastest way)
val = df.at[3, 'Score']

# Q: Update single cell efficiently
df.at[0, 'Grade'] = 'A+'
```

**⚠️ Common Mistakes:**
```python
# ❌ at/iat only for SINGLE values, not slices
df.at[0:2, 'Name']    # TypeError! Use loc for slices

# ❌ Don't confuse at (label) with iat (position)
df.iat[0, 'Name']     # TypeError! iat needs integer column position
```

---

### `query()` — Query string

```python
df.query('Score > 80')
df.query('Score > 80 and Grade == "A"')
df.query('City in ["Delhi", "Mumbai"]')

# use @ to reference Python variables
threshold = 75
df.query('Score > @threshold')
```

**📝 Exam Examples:**
```python
# Q: Filter students with score between 70 and 90
df.query('70 <= Score <= 90')

# Q: Filter using external variable
min_score = 80
df.query('Score >= @min_score')
```

**⚠️ Common Mistakes:**
```python
# ❌ Column names with spaces need backticks in query
df.query('Student Name == "Alice"')     # SyntaxError!
df.query('`Student Name` == "Alice"')   # ✅

# ❌ String values need quotes inside the query string
df.query('Grade == A')      # wrong
df.query('Grade == "A"')    # ✅
```

---

### `isin()` — Check membership

```python
df[df['City'].isin(['Delhi', 'Mumbai'])]
df[~df['City'].isin(['Delhi', 'Mumbai'])]    # NOT in list
```

**📝 Exam Examples:**
```python
# Q: Filter employees from IT or HR department
df[df['Dept'].isin(['IT', 'HR'])]

# Q: Exclude certain IDs
df[~df['ID'].isin([101, 102, 105])]
```

---

### `filter()` — Subset items

```python
df.filter(items=['Name', 'Score'])          # keep only these columns
df.filter(like='score', axis=1)             # columns containing 'score'
df.filter(regex='^S', axis=1)              # columns starting with 'S'
```

**⚠️ Common Mistakes:**
```python
# ❌ filter() filters LABELS (columns/index), not values!
df.filter(items=['Name'])     # keeps column 'Name' — doesn't filter rows by Name value
# Use boolean indexing to filter rows by values
```

---

### `drop()` — Drop rows or columns

```python
df.drop('Name', axis=1)                  # drop column
df.drop(['A', 'B'], axis=1)             # drop multiple columns
df.drop(0, axis=0)                      # drop row by index
df.drop(index=[0, 1])                   # drop rows
df.drop(columns=['A', 'B'])             # explicit columns keyword
```

**📝 Exam Examples:**
```python
# Q: Remove 'Email' and 'Phone' columns
df.drop(columns=['Email', 'Phone'])

# Q: Drop row with index 5
df.drop(index=5)
```

**⚠️ Common Mistakes:**
```python
# ❌ drop() returns new df — doesn't modify in place!
df.drop('col', axis=1)             # df is UNCHANGED
df = df.drop('col', axis=1)        # ✅ reassign
df.drop('col', axis=1, inplace=True)  # ✅ or inplace

# ❌ Wrong axis
df.drop('Name', axis=0)    # tries to find row labeled 'Name' — KeyError!
df.drop('Name', axis=1)    # ✅ drops column named 'Name'
```

---

### `rename()` — Rename items

```python
df.rename(columns={'old_name': 'new_name'})
df.rename(columns={'A': 'Alpha', 'B': 'Beta'})
df.rename(index={0: 'first', 1: 'second'})
```

**📝 Exam Examples:**
```python
# Q: Rename 'Marks' to 'Score' and 'Roll' to 'ID'
df.rename(columns={'Marks': 'Score', 'Roll': 'ID'}, inplace=True)
```

**⚠️ Common Mistakes:**
```python
# ❌ rename() doesn't modify in place by default!
df.rename(columns={'old': 'new'})       # returns new df, df unchanged
df = df.rename(columns={'old': 'new'})  # ✅
```

---

### `set_index()` / `reset_index()`

```python
df.set_index('ID')             # make 'ID' the index
df.set_index(['ID', 'Date'])   # multi-level index
df.reset_index()               # bring index back as column
df.reset_index(drop=True)      # drop old index completely
```

**📝 Exam Examples:**
```python
# Q: Set 'StudentID' as index
df = df.set_index('StudentID')

# Q: Reset index after filtering (to get clean 0,1,2... index)
filtered = df[df['Score'] > 80].reset_index(drop=True)
```

**⚠️ Common Mistakes:**
```python
# ❌ After set_index, the column is REMOVED from df
df = df.set_index('ID')
df['ID']    # KeyError! ID is now the index, not a column

# ❌ reset_index without drop=True brings old index as a column
df.reset_index()          # old index becomes a column
df.reset_index(drop=True) # ✅ discard old index
```

---

### `where()` / `mask()`

```python
df['Score'].where(df['Score'] >= 50, other=0)   # keep values ≥50, replace rest with 0
df['Score'].mask(df['Score'] < 50, other=0)     # replace values <50 with 0
```

**⚠️ Common Mistakes:**
```python
# ❌ where vs mask are OPPOSITES — easy to confuse!
# where: keeps where condition is TRUE, replaces where FALSE
# mask:  replaces where condition is TRUE, keeps where FALSE

df['col'].where(df['col'] > 0)  # keeps positive, sets negative to NaN
df['col'].mask(df['col'] > 0)   # sets positive to NaN, keeps negative
```

---

### `between()`

```python
df[df['Score'].between(60, 80)]              # inclusive by default
df[df['Score'].between(60, 80, inclusive='left')]   # 60 included, 80 not
```

**📝 Exam Examples:**
```python
# Q: Select students with scores between 70 and 85 (inclusive)
df[df['Score'].between(70, 85)]
```

---

## 🧹 CLEANING — Handling Messy Data

### `isna()` / `notna()` — Detect missing values

```python
df.isna()                    # True where NaN
df.isna().sum()              # count NaN per column
df.isna().sum().sum()        # total NaN in entire df
df['col'].isna()             # boolean Series
df[df['col'].notna()]        # rows where col is NOT null
```

**📝 Exam Examples:**
```python
# Q: Count missing values in each column
df.isna().sum()

# Q: Which rows have missing 'Email'?
df[df['Email'].isna()]

# Q: What percentage of data is missing?
(df.isna().sum() / len(df)) * 100
```

---

### `dropna()` — Drop missing values

```python
df.dropna()                        # drop rows with ANY NaN
df.dropna(axis=1)                  # drop columns with ANY NaN
df.dropna(how='all')               # drop rows where ALL values are NaN
df.dropna(subset=['Email', 'Age']) # drop rows with NaN in these columns only
df.dropna(thresh=3)                # keep rows with at least 3 non-NaN values
```

**📝 Exam Examples:**
```python
# Q: Remove rows missing 'Score' or 'Name'
df.dropna(subset=['Score', 'Name'])

# Q: Remove columns that are entirely empty
df.dropna(axis=1, how='all')
```

**⚠️ Common Mistakes:**
```python
# ❌ dropna() doesn't modify in place
df.dropna()                  # df unchanged!
df = df.dropna()             # ✅

# ❌ dropna() default drops row if ANY column is NaN
df.dropna()   # may lose too many rows
df.dropna(subset=['important_col'])  # ✅ only drop if specific col is NaN
```

---

### `fillna()` — Fill missing values

```python
df.fillna(0)                          # fill all NaN with 0
df['Score'].fillna(df['Score'].mean()) # fill with mean
df.fillna(method='ffill')             # forward fill (propagate last valid)
df.fillna(method='bfill')             # backward fill
df.fillna({'Age': 0, 'City': 'Unknown'})  # different fill per column
```

**📝 Exam Examples:**
```python
# Q: Replace missing scores with the mean score
df['Score'] = df['Score'].fillna(df['Score'].mean())

# Q: Fill missing city with 'Unknown'
df['City'] = df['City'].fillna('Unknown')

# Q: Forward fill time series
df['Price'] = df['Price'].fillna(method='ffill')
```

**⚠️ Common Mistakes:**
```python
# ❌ fillna() doesn't modify in place by default
df['col'].fillna(0)          # col unchanged!
df['col'] = df['col'].fillna(0)  # ✅

# ❌ Using mean to fill non-numeric columns
df['Name'].fillna(df['Name'].mean())   # AttributeError! Strings have no mean
df['Name'].fillna('Unknown')           # ✅
```

---

### `interpolate()` — Interpolate missing values

```python
df['Value'].interpolate()                    # linear interpolation (default)
df['Value'].interpolate(method='polynomial', order=2)
df['Value'].interpolate(method='ffill')
```

**📝 Exam Examples:**
```python
# Q: Fill missing values using linear interpolation
df['Temperature'] = df['Temperature'].interpolate()
```

---

### `duplicated()` / `drop_duplicates()`

```python
df.duplicated()                          # True for duplicate rows
df.duplicated(subset=['Name', 'Email'])  # check specific columns
df.duplicated(keep='last')               # mark first as duplicate instead

df.drop_duplicates()                     # remove duplicate rows
df.drop_duplicates(subset=['Email'])     # based on one column
df.drop_duplicates(keep='last')          # keep last occurrence
```

**📝 Exam Examples:**
```python
# Q: How many duplicate rows exist?
df.duplicated().sum()

# Q: Remove rows with duplicate emails (keep first)
df.drop_duplicates(subset=['Email'], keep='first')
```

**⚠️ Common Mistakes:**
```python
# ❌ duplicated() marks the SECOND (and later) duplicates as True by default
# ❌ The FIRST occurrence is marked False (not a duplicate by default)
df.duplicated(keep=False)   # marks ALL duplicates as True (including first)
```

---

### `astype()` — Cast data type

```python
df['Age'] = df['Age'].astype(int)
df['Score'] = df['Score'].astype(float)
df['Is_Pass'] = df['Is_Pass'].astype(bool)
df['Category'] = df['Category'].astype('category')
```

**📝 Exam Examples:**
```python
# Q: Convert 'Age' column from float to int
df['Age'] = df['Age'].astype(int)

# Q: Convert 'ID' to string
df['ID'] = df['ID'].astype(str)
```

**⚠️ Common Mistakes:**
```python
# ❌ Can't cast NaN to int!
df['Age'].astype(int)    # ValueError if any NaN in 'Age'
df['Age'].fillna(0).astype(int)   # ✅ fill NaN first

# ❌ Casting 'Yes'/'No' strings to bool doesn't work as expected
df['Pass'].astype(bool)   # 'No' → True (non-empty string is True!)
# ✅ Use map instead
df['Pass'].map({'Yes': True, 'No': False})
```

---

### `replace()` — Replace values

```python
df.replace(0, np.nan)                           # replace 0 with NaN
df['Grade'].replace('A', 'Excellent')           # in a column
df.replace({'Grade': {'A': 'Excellent', 'B': 'Good'}})  # nested dict
df.replace([1, 2], [10, 20])                    # replace list with list
```

**📝 Exam Examples:**
```python
# Q: Replace 'Male'/'Female' with 1/0 in Gender column
df['Gender'].replace({'Male': 1, 'Female': 0})

# Q: Replace all zeros in DataFrame with NaN
import numpy as np
df.replace(0, np.nan)
```

**⚠️ Common Mistakes:**
```python
# ❌ replace() is not inplace by default!
df.replace('?', np.nan)          # df unchanged!
df = df.replace('?', np.nan)     # ✅

# ❌ replace() needs exact match — use regex for partial
df.replace('N/A', np.nan)        # replaces only exact 'N/A'
df.replace(r'^\s*$', np.nan, regex=True)  # ✅ replace whitespace-only cells
```

---

### `clip()` — Trim outliers

```python
df['Score'].clip(0, 100)          # cap values between 0 and 100
df.clip(lower=0)                  # set minimum to 0
df.clip(upper=df.quantile(0.95))  # clip at 95th percentile
```

**📝 Exam Examples:**
```python
# Q: Remove outliers by capping scores between 0 and 100
df['Score'] = df['Score'].clip(0, 100)
```

---

### `convert_dtypes()` / `infer_objects()`

```python
df = df.convert_dtypes()    # convert to best nullable dtypes
df = df.infer_objects()     # infer better types for object columns
```

---

## 🔄 TRANSFORMATION — Reshaping Data

### `apply()` — Apply function

```python
df['Score'].apply(lambda x: x * 2)
df.apply(lambda col: col.max() - col.min())    # per column
df.apply(lambda row: row['A'] + row['B'], axis=1)  # per row
```

**📝 Exam Examples:**
```python
# Q: Add 'Grade' column: 'Pass' if Score >= 50, else 'Fail'
df['Grade'] = df['Score'].apply(lambda x: 'Pass' if x >= 50 else 'Fail')

# Q: Create a custom function and apply per row
def score_label(row):
    if row['Score'] >= 90: return 'A'
    elif row['Score'] >= 75: return 'B'
    else: return 'C'

df['Label'] = df.apply(score_label, axis=1)
```

**⚠️ Common Mistakes:**
```python
# ❌ Forgetting axis=1 for row-wise apply
df.apply(lambda row: row['A'] + row['B'])          # applies per COLUMN
df.apply(lambda row: row['A'] + row['B'], axis=1)  # ✅ per row

# ❌ apply() on a Series vs DataFrame — different behavior
df['col'].apply(func)   # applies to each value
df.apply(func)          # applies to each column (Series)
```

---

### `map()` — Map values (Series)

```python
s.map({'A': 1, 'B': 2})       # replace using dict
s.map(lambda x: x * 2)        # apply function
s.map(lambda x: x.lower())    # transform each value
```

**📝 Exam Examples:**
```python
# Q: Encode 'Gender' as numeric
df['Gender'] = df['Gender'].map({'Male': 1, 'Female': 0})

# Q: Extract domain from email
df['Domain'] = df['Email'].map(lambda x: x.split('@')[1])
```

**⚠️ Common Mistakes:**
```python
# ❌ map() is for Series; applymap() was for DataFrame elementwise
# In newer pandas: use df.map() for DataFrame instead of applymap()
df['col'].map(func)    # ✅ on Series
df.map(func)           # ✅ on DataFrame (elementwise) — replaces applymap()
```

---

### `applymap()` — Elementwise (deprecated → use `map()`)

```python
df.applymap(lambda x: round(x, 2))    # older pandas
df.map(lambda x: round(x, 2))         # newer pandas (>= 2.1)
```

---

### `transform()` — Transform keeping shape

```python
df['Normalized'] = df.groupby('Class')['Score'].transform(lambda x: (x - x.mean()) / x.std())
df['Score'].transform(lambda x: x - x.mean())   # center the values
```

**📝 Exam Examples:**
```python
# Q: Normalize scores within each class group
df['Z_Score'] = df.groupby('Class')['Score'].transform(
    lambda x: (x - x.mean()) / x.std()
)
```

---

### `melt()` — Wide to Long format

```python
pd.melt(df, id_vars=['Name'], value_vars=['Math', 'Science'])
pd.melt(df, id_vars=['ID'], var_name='Subject', value_name='Marks')
```

**📝 Exam Examples:**
```python
# Q: Reshape scores table (Math, Science as columns) into long format
df_long = pd.melt(df, id_vars=['Student'], 
                  value_vars=['Math', 'Science', 'English'],
                  var_name='Subject', value_name='Score')
```

**⚠️ Common Mistakes:**
```python
# ❌ Forgetting id_vars — melts all columns
pd.melt(df)   # melts everything including identifier columns

# ✅ Always specify id_vars for identifier columns to keep
pd.melt(df, id_vars=['ID', 'Name'])
```

---

### `pivot()` — Long to Wide format

```python
df.pivot(index='Student', columns='Subject', values='Score')
```

**📝 Exam Examples:**
```python
# Q: Convert long format (Student, Subject, Score) to wide (Student as rows, Subjects as cols)
df_wide = df.pivot(index='Student', columns='Subject', values='Score')
```

**⚠️ Common Mistakes:**
```python
# ❌ pivot() fails with duplicate entries!
df.pivot(index='Student', columns='Subject', values='Score')
# ValueError if same (Student, Subject) combo appears twice

# ✅ Use pivot_table() for duplicates (it aggregates)
df.pivot_table(index='Student', columns='Subject', values='Score', aggfunc='mean')
```

---

### `pivot_table()` — Pivot with aggregation

```python
pd.pivot_table(df, values='Score', index='Class', columns='Subject', aggfunc='mean')
pd.pivot_table(df, values='Sales', index='Region', aggfunc=['mean', 'sum'])
pd.pivot_table(df, values='Score', index='Class', aggfunc='mean', margins=True)  # adds totals
```

**📝 Exam Examples:**
```python
# Q: Average score per class per subject
pd.pivot_table(df, values='Score', index='Class', columns='Subject', aggfunc='mean')

# Q: Total sales by region with grand total
pd.pivot_table(df, values='Sales', index='Region', aggfunc='sum', margins=True)
```

---

### `stack()` / `unstack()`

```python
df.stack()      # columns → inner row index (wide to long)
df.unstack()    # inner row index → columns (long to wide)
```

**📝 Exam Examples:**
```python
# After pivot, stack to get long format back
pivoted = df.pivot(index='A', columns='B', values='C')
long_again = pivoted.stack()
```

---

### `explode()` — Explode list column

```python
df = pd.DataFrame({'Name': ['Alice', 'Bob'], 'Subjects': [['Math', 'Sci'], ['Eng']]})
df.explode('Subjects')   # each list item becomes its own row
```

**📝 Exam Examples:**
```python
# Q: Expand a column containing lists so each element is a separate row
df.explode('Tags')
```

---

### `get_dummies()` — One-hot encoding

```python
pd.get_dummies(df['Color'])                     # creates 0/1 columns
pd.get_dummies(df, columns=['Color', 'Size'])   # encode multiple columns
pd.get_dummies(df['Color'], drop_first=True)    # avoid multicollinearity
```

**📝 Exam Examples:**
```python
# Q: Encode 'City' column for machine learning
df_encoded = pd.get_dummies(df, columns=['City'])

# Q: One-hot encode Grade column, drop first to avoid dummy trap
pd.get_dummies(df['Grade'], drop_first=True)
```

**⚠️ Common Mistakes:**
```python
# ❌ Forgetting drop_first for regression models (dummy variable trap)
pd.get_dummies(df['Gender'])               # 2 columns: Male, Female
pd.get_dummies(df['Gender'], drop_first=True)  # ✅ 1 column: Male (0/1)
```

---

### `crosstab()` — Frequency table

```python
pd.crosstab(df['Gender'], df['Grade'])
pd.crosstab(df['Gender'], df['Grade'], normalize='index')   # row-wise proportions
pd.crosstab(df['Gender'], df['Grade'], margins=True)        # add totals
```

---

### `cut()` / `qcut()` — Binning

```python
pd.cut(df['Score'], bins=3)                          # equal-width bins
pd.cut(df['Score'], bins=[0, 50, 75, 100], labels=['Low', 'Mid', 'High'])
pd.qcut(df['Score'], q=4)                            # equal-frequency (quartile) bins
pd.qcut(df['Score'], q=4, labels=['Q1','Q2','Q3','Q4'])
```

**📝 Exam Examples:**
```python
# Q: Categorize scores into 'Low', 'Medium', 'High'
df['Category'] = pd.cut(df['Score'], 
                         bins=[0, 60, 80, 100], 
                         labels=['Low', 'Medium', 'High'])

# Q: Divide into 4 equal-frequency groups
df['Quartile'] = pd.qcut(df['Score'], q=4, labels=['Q1','Q2','Q3','Q4'])
```

**⚠️ Common Mistakes:**
```python
# ❌ cut() vs qcut() confusion:
# cut() = equal WIDTH bins (0-33, 33-66, 66-100)
# qcut() = equal FREQUENCY bins (same count in each bin)

# ❌ Values outside bin range become NaN in cut()
pd.cut([50, 150], bins=[0, 100])   # 150 becomes NaN!
pd.cut([50, 150], bins=[0, 200])   # ✅ ensure range covers all values
```

---

### String methods (`str.*`)

```python
df['Name'].str.lower()
df['Name'].str.upper()
df['Name'].str.contains('ali', case=False)    # regex match
df['Email'].str.split('@')                    # returns list in each cell
df['Email'].str.split('@', expand=True)       # expand into columns
df['Name'].str.len()
df['Name'].str.strip()
df['Name'].str.replace('  ', ' ')
```

**📝 Exam Examples:**
```python
# Q: Find all emails from gmail
df[df['Email'].str.contains('@gmail.com')]

# Q: Extract username from email (before @)
df['Username'] = df['Email'].str.split('@').str[0]

# Q: Filter names starting with 'A'
df[df['Name'].str.startswith('A')]

# Q: Count characters in each name
df['Name_Length'] = df['Name'].str.len()
```

**⚠️ Common Mistakes:**
```python
# ❌ str methods need the .str accessor on the column
df['Name'].lower()          # AttributeError!
df['Name'].str.lower()      # ✅

# ❌ str.contains returns NaN for NaN values (not False!)
df[df['col'].str.contains('x')]           # error if NaN present
df[df['col'].str.contains('x', na=False)] # ✅ treat NaN as False
```

---

## 📦 AGGREGATION — Grouping & Windows

### `groupby()` — Group data

```python
df.groupby('Class')['Score'].mean()
df.groupby(['Class', 'Gender'])['Score'].mean()
df.groupby('Class').agg({'Score': 'mean', 'Age': 'max'})
```

**📝 Exam Examples:**
```python
# Q: Average score per class
df.groupby('Class')['Score'].mean()

# Q: Count students per department per gender
df.groupby(['Dept', 'Gender'])['ID'].count()

# Q: Multiple aggregations at once
df.groupby('Class').agg(
    avg_score=('Score', 'mean'),
    max_score=('Score', 'max'),
    count=('Score', 'count')
)
```

**⚠️ Common Mistakes:**
```python
# ❌ groupby result is a GroupBy object, not a DataFrame yet
g = df.groupby('Class')     # GroupBy object — can't display directly
g['Score'].mean()            # ✅ apply aggregation to get result

# ❌ groupby drops NaN keys by default
df.groupby('City', dropna=False)['Score'].mean()  # ✅ include NaN groups
```

---

### `agg()` — Aggregate

```python
df.groupby('Class')['Score'].agg(['mean', 'std', 'count'])
df.groupby('Class').agg({'Score': ['mean', 'max'], 'Age': 'min'})
```

**📝 Exam Examples:**
```python
# Q: Get mean, min, and max of Score grouped by Class
df.groupby('Class')['Score'].agg(['mean', 'min', 'max'])

# Q: Named aggregation (pandas >= 0.25)
result = df.groupby('Class').agg(
    Mean_Score=('Score', 'mean'),
    Total=('Score', 'sum')
)
```

---

### `rolling()` — Rolling window

```python
df['Price'].rolling(window=3).mean()    # 3-period moving average
df['Price'].rolling(window=7).sum()
df['Price'].rolling(window=3).std()
```

**📝 Exam Examples:**
```python
# Q: Calculate 7-day moving average of sales
df['MA7'] = df['Sales'].rolling(window=7).mean()

# Q: Rolling sum of last 3 days
df['Rolling_Sum'] = df['Revenue'].rolling(window=3).sum()
```

**⚠️ Common Mistakes:**
```python
# ❌ First (window-1) values will be NaN
df['MA3'] = df['Price'].rolling(3).mean()
# First 2 rows will be NaN because not enough history yet

# ❌ rolling() needs data to be sorted by time first!
df = df.sort_values('Date')
df['MA'] = df['Price'].rolling(7).mean()  # ✅
```

---

### `expanding()` — Expanding window

```python
df['Price'].expanding().mean()    # cumulative mean (grows with each row)
df['Price'].expanding().sum()     # cumulative sum
```

**📝 Exam Examples:**
```python
# Q: Cumulative average of sales up to each date
df['Cumulative_Avg'] = df['Sales'].expanding().mean()
```

---

### `ewm()` — Exponentially weighted

```python
df['Price'].ewm(span=3).mean()    # exponential moving average
df['Price'].ewm(alpha=0.3).mean() # specify decay factor
```

---

## 🔗 MERGING — Combining DataFrames

### `merge()` — Join DataFrames

```python
# Inner join — only matching rows
pd.merge(df1, df2, on='ID')
pd.merge(df1, df2, on='ID', how='inner')

# Left join — all rows from left
pd.merge(df1, df2, on='ID', how='left')

# Right join — all rows from right
pd.merge(df1, df2, on='ID', how='right')

# Outer join — all rows from both
pd.merge(df1, df2, on='ID', how='outer')

# Different column names
pd.merge(df1, df2, left_on='StudentID', right_on='ID')
```

**📝 Exam Examples:**
```python
# Q: Join students and scores tables on 'ID'
result = pd.merge(students, scores, on='ID', how='inner')

# Q: Left join to keep all students even if no score
result = pd.merge(students, scores, on='StudentID', how='left')

# Q: Merge on two columns
result = pd.merge(df1, df2, on=['Year', 'Month'])
```

**⚠️ Common Mistakes:**
```python
# ❌ Forgetting 'on' parameter when column names differ
pd.merge(df1, df2)               # tries to match ALL common columns!
pd.merge(df1, df2, on='ID')     # ✅ explicit

# ❌ Inner join silently drops non-matching rows!
pd.merge(df1, df2, on='ID')                  # loses unmatched
pd.merge(df1, df2, on='ID', how='left')      # ✅ keep all of df1

# ❌ Duplicate column names get suffixes
pd.merge(df1, df2, on='ID')   # if both have 'Name': Name_x, Name_y
pd.merge(df1, df2, on='ID', suffixes=('_student', '_teacher'))  # ✅ custom suffixes
```

---

### `join()` — Join on index

```python
df1.join(df2)                         # join on index
df1.join(df2, how='left')
df1.join(df2, on='ID')               # join using df1 column, df2 index
```

**⚠️ Common Mistakes:**
```python
# ❌ join() uses INDEX by default, not columns!
df1.join(df2)    # joins on df2's index
# ✅ Use merge() for column-based joins — clearer and more flexible
```

---

### `concat()` — Concatenate

```python
pd.concat([df1, df2])                         # stack rows (axis=0)
pd.concat([df1, df2], ignore_index=True)      # reset index
pd.concat([df1, df2], axis=1)                 # side by side (axis=1)
pd.concat([df1, df2], join='inner')           # only common columns
```

**📝 Exam Examples:**
```python
# Q: Combine two tables with same columns (append rows)
df_all = pd.concat([df_jan, df_feb], ignore_index=True)

# Q: Add new columns from another df
df_combined = pd.concat([df1, df2], axis=1)
```

**⚠️ Common Mistakes:**
```python
# ❌ Forgetting ignore_index — gets duplicate index values
pd.concat([df1, df2])                     # index: 0,1,2,0,1,2 (duplicates!)
pd.concat([df1, df2], ignore_index=True)  # ✅ index: 0,1,2,3,4,5

# ❌ Mismatched columns with concat
# Missing columns get NaN by default (join='outer')
pd.concat([df1, df2], join='inner')   # ✅ only keep common columns
```

---

### `combine_first()`

```python
df1.combine_first(df2)   # fill NaN in df1 with values from df2
```

**📝 Exam Examples:**
```python
# Q: Fill missing values in df1 using df2 as fallback
df_complete = df1.combine_first(df2)
```

---

## ⏰ TIME — Date & Time Operations

### `to_datetime()` — Convert to datetime

```python
pd.to_datetime(df['Date'])
pd.to_datetime(df['Date'], format='%d/%m/%Y')
pd.to_datetime(df['Date'], errors='coerce')    # invalid → NaT instead of error
```

**📝 Exam Examples:**
```python
# Q: Convert 'Date' column to datetime
df['Date'] = pd.to_datetime(df['Date'])

# Q: Convert with custom format
df['Date'] = pd.to_datetime(df['Date'], format='%d-%m-%Y')
```

**⚠️ Common Mistakes:**
```python
# ❌ Datetime string not recognized — must specify format
pd.to_datetime('25/12/2023')                          # may fail or parse wrong
pd.to_datetime('25/12/2023', format='%d/%m/%Y')       # ✅

# ❌ Bad dates cause errors unless errors='coerce'
pd.to_datetime(['2023-01-01', 'not_a_date'])           # ValueError!
pd.to_datetime(['2023-01-01', 'not_a_date'], errors='coerce')  # ✅ → NaT
```

---

### `dt.*` — Datetime accessor

```python
df['Date'].dt.year
df['Date'].dt.month
df['Date'].dt.day
df['Date'].dt.day_name()     # 'Monday', 'Tuesday'...
df['Date'].dt.quarter
df['Date'].dt.hour
df['Date'].dt.weekday        # 0=Monday, 6=Sunday
```

**📝 Exam Examples:**
```python
# Q: Extract year and month into separate columns
df['Year'] = df['Date'].dt.year
df['Month'] = df['Date'].dt.month

# Q: Filter records from weekends only
df[df['Date'].dt.weekday >= 5]    # 5=Saturday, 6=Sunday

# Q: Get day name
df['Day'] = df['Date'].dt.day_name()
```

**⚠️ Common Mistakes:**
```python
# ❌ dt accessor only works on datetime dtype!
df['Date'].dt.year      # AttributeError if Date is still a string object

# ✅ Convert first
df['Date'] = pd.to_datetime(df['Date'])
df['Year'] = df['Date'].dt.year
```

---

### `shift()` — Shift data

```python
df['Price'].shift(1)     # shift down by 1 (previous value)
df['Price'].shift(-1)    # shift up by 1 (next value)
```

**📝 Exam Examples:**
```python
# Q: Calculate change from previous day
df['Prev_Price'] = df['Price'].shift(1)
df['Change'] = df['Price'] - df['Prev_Price']
```

---

### `diff()` — Difference

```python
df['Price'].diff()      # difference with previous row
df['Price'].diff(2)     # difference with row 2 periods ago
```

**📝 Exam Examples:**
```python
# Q: Calculate daily change in stock price
df['Daily_Change'] = df['Price'].diff()

# Q: Week-over-week change (7-period diff)
df['WoW_Change'] = df['Sales'].diff(7)
```

---

### `pct_change()` — Percent change

```python
df['Price'].pct_change()       # % change from previous row
df['Price'].pct_change() * 100 # as percentage
```

**📝 Exam Examples:**
```python
# Q: Calculate daily return of a stock
df['Daily_Return'] = df['Price'].pct_change() * 100

# Q: Month-over-month % change
df['MoM'] = df['Revenue'].pct_change(periods=30)
```

**⚠️ Common Mistakes:**
```python
# ❌ First row is always NaN (no previous value to compare)
df['Return'] = df['Price'].pct_change()   # row 0 = NaN

# ❌ pct_change returns decimal (0.05 = 5%), not percentage directly
df['Price'].pct_change()       # 0.05 = 5% change
df['Price'].pct_change() * 100 # ✅ multiply to get percent
```

---

### `resample()` — Resample time series

```python
# Must have DatetimeIndex first
df = df.set_index('Date')

df.resample('M').mean()    # monthly average
df.resample('W').sum()     # weekly sum
df.resample('D').last()    # daily last value
df.resample('Q').sum()     # quarterly sum
```

**📝 Exam Examples:**
```python
# Q: Get monthly total sales from daily data
df = df.set_index('Date')
monthly = df['Sales'].resample('M').sum()

# Q: Downscale hourly data to daily averages
daily_avg = df['Temp'].resample('D').mean()
```

**⚠️ Common Mistakes:**
```python
# ❌ resample() requires DatetimeIndex!
df.resample('M').mean()    # TypeError if index is not datetime

# ✅ Set datetime index first
df['Date'] = pd.to_datetime(df['Date'])
df = df.set_index('Date')
df.resample('M').mean()   # ✅

# Frequency aliases: 'D'=day, 'W'=week, 'M'=month end, 'MS'=month start,
#                    'Q'=quarter, 'A'=year, 'H'=hour, 'T'=minute
```

---

## 🧠 Quick Reference — Top Exam Gotchas

| Mistake | Wrong | Right |
|--------|-------|-------|
| `shape` is attribute | `df.shape()` | `df.shape` |
| `dtypes` is attribute | `df.dtypes()` | `df.dtypes` |
| `loc` is inclusive | `df.loc[0:3]` → 4 rows | Know it's 0,1,2,3 |
| `iloc` is exclusive | `df.iloc[0:3]` → 3 rows | Know it's 0,1,2 |
| `mode()` returns Series | `df['col'].mode()` | `df['col'].mode()[0]` |
| `drop()` not inplace | `df.drop('col', axis=1)` | `df = df.drop(...)` |
| `fillna()` not inplace | `df['col'].fillna(0)` | `df['col'] = df['col'].fillna(0)` |
| `read_html()` returns list | `pd.read_html('url')` | `pd.read_html('url')[0]` |
| `count()` skips NaN | `df['col'].count()` | Use `len(df)` for all rows |
| `astype(int)` with NaN | `df['col'].astype(int)` | Fill NaN first! |
| `str.*` needs accessor | `df['col'].lower()` | `df['col'].str.lower()` |
| `pct_change()` is decimal | `df.pct_change()` → 0.05 | Multiply by 100 for % |
| `resample` needs DT index | `df.resample('M')` | Set DatetimeIndex first |
| `merge()` inner drops rows | `pd.merge(df1, df2, on='id')` | Use `how='left'` if needed |
| `concat` duplicate index | `pd.concat([df1, df2])` | Add `ignore_index=True` |

---

> 💡 **Pro Tip for Exams:** When in doubt, remember that most pandas methods return a **new object** and don't modify in-place. Always reassign (`df = df.method()`) or use `inplace=True` (where supported).
