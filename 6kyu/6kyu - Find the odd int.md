## Find the odd int - 6kyu

**Instructions**

- Given an array of integers, find the one that appears an odd number of times.

- There will always be only one integer that appears an odd number of times.

---

#### Test cases

```python
print(find_it([20,1,-1,2,-2,3,3,5,5,1,2,4,20,4,-1,-2,5]))
print(find_it([1,1,2,-2,5,2,4,4,-1,-2,5]))
print(find_it([20,1,1,2,2,3,3,5,5,4,20,4,5]))
print(find_it([10]))
print(find_it([1,1,1,1,1,1,10,1,1,1,1]))
print(find_it([5,4,3,2,1,5,4,3,2,10,10]))
```

#### Output

```
5
-1
5
10
10
1
```

---

#### Solution

```python
def find_it(seq):
    return next(i for i in set(seq) if seq.count(i) & 1)
```

---

[Codewars link](https://www.codewars.com/kata/54da5a58ea159efa38000836)
