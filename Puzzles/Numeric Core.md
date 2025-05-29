![[Pasted image 20250511184627.png]]
![[Pasted image 20250511184634.png]]
+3,  -6, /1, \*4 = -12


[[Wine Cellar]]
1213:
1, 2, 1, 3
+1\*2/1-3 = -2
+1-2/1\*3 = -3

By blue memo in [[Mechanarium]]: On the coat of arms the first number is one numeral, the rest are each two numerals
M CC XI II
1000, 200, 11, 2
+1000/200\*11-2=53


Deed in [[Room 46]]
05121912

[[Testament]] date:
18 03 19 93

![[Pasted image 20250527002026.png]]
```python
import math

words = ["pigs", "sand", "mail", "date", "head", "clam", "peak", "heat", "joya", "well", "toad", "card", "will", "tape", "legs", "tree", "road", "maid", "slab", "rock", "hand", "vase", "safe", "clay", "toes"]
out = []

for word in words:
    nums = []
    for c in word:
        v = ord(c) - ord('a') + 1
        nums.append(v)
    possibilities = []
    possibilities.append((nums[0] * nums[1] / nums[2]) - nums[3])
    possibilities.append((nums[0] * nums[1] - nums[2]) / nums[3])
    possibilities.append(nums[0] / nums[1] * nums[2] - nums[3])
    possibilities.append((nums[0] / nums[1] - nums[2]) * nums[3])
    possibilities.append((nums[0] - nums[1]) / nums[2] * nums[3])
    possibilities.append((nums[0] - nums[1]) * nums[2] / nums[3])

    out.append(chr(math.floor(sorted(filter(lambda n: n==math.floor(n) and n > 0, possibilities))[0])+ord('a')-1))
print(out)

# Outputs:
# ['s', 't', 'i', 'l', 'l', 'w', 'a', 't', 'e', 'r', 't', 'i', 'n', 't', 's', 'b', 'l', 'a', 'n', 'k', 'b', 'o', 'o', 'k', 's']
```