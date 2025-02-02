## Correct the time-string - 7kyu

**Instructions**

- You have to create a method, that corrects a given time string.

- There was a problem in addition, so many of the time strings are broken.

- Time is formatted using the 24-hour clock, so from `00:00:00` to `23:59:59`.

```
"09:10:01" -> "09:10:01"
"11:70:10" -> "12:10:10"
"19:99:99" -> "20:40:39"
"24:01:01" -> "00:01:01"
```

- If the input-string is empty, return `''`.

- If the time-string-format is invalid, return `None`.

---

#### Test cases

```python
print(time_correct("001122"))
print(time_correct("09:10:01"))
print(time_correct("11:70:10"))
print(time_correct("19:99:99"))
```

#### Output

```
None
09:10:01
12:10:10
20:40:39
```

---

#### Solution

```python
import re

def time_correct(t):
    if not t or not bool(re.match(r'\d\d:\d\d:\d\d', t)):
        return '' if t == '' else None

    h, m, s = map(int, t.split(':'))

    if s >= 60: s -= 60; m += 1
    if m >= 60: m -= 60; h += 1
    return f'{ h %24:0>2}:{m:0>2}:{s:0>2}'
```

---

[Codewars link](https://www.codewars.com/kata/57873ab5e55533a2890000c7)
