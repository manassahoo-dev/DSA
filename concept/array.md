**Prefix Sum**

Prefix sum is the technique where you precompute & store the cumulative sum of the sequence of elements that allows fast sum calculation of any continuous range.

Let's say we have a sequence of elements A as mentioned below
A = {a0, a1, a2, a3, a4, a5}

so Prefix Sum P will be calculated as
P = {p0, p1, p2, p3, p4, p5}

``` 
where-
p0 = a0
p1 = a1 + a0
p2 = a0 + a1 + a2
p3 = a0 + a1 + a2 + a3 
p4 = a0 + a1 + a2 + a3 + a4
p5 = a0 + a1 + a2 + a3 + a4 + a5


Q) Say we need to sum get sum of all elements from indices 
[2 to 5] => [a2 + a3 + a4 + a5]		or	[p5 - p1] 
[1 to 4] => [a1 + a2 + a3 + a4] 	or	[p4 - p1]
[0 to 4] => [a0 + a1 + a2 + a3 + a4] 	or 	[p4]
```
- **Prefix Sum Formula**
- **Range Sum Query**
- **In-place Prefix Sum**
