## Cat and Mouse - 7kyu

**Instructions**

- You will be given a string (x) featuring a cat 'C' and a mouse 'm'.

- The rest of the string will be made up of '.'.

- You need to find out if the cat can catch the mouse from it's current position. The cat can jump over three characters. So:

- C.....m returns 'Escaped!', as there are more than three characters between

- C...m returns 'Caught!', as there are three characters between the two, the cat can jump.

---

#### Test cases

```python
print(cat_mouse('C....m'))
print(cat_mouse('C..m'))
print(cat_mouse('C.....m'))
print(cat_mouse('C.m'))
print(cat_mouse('m...C'))
```

#### Output

```
Escaped!
Caught!
Escaped!
Caught!
Caught!
```

---

#### Solution

```python
import re

def cat_mouse(x):
    obs = len(re.findall(r'[Cm](.*)[Cm]', x)[0])
    return ('Escaped!', 'Caught!')[obs <= 3]
```

---

[Codewars link](https://www.codewars.com/kata/57ee24e17b45eff6d6000164)
