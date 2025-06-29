```python
from collections import defaultdict


# easier:
hashmap = defaultdict(int)

for ltr in word:
	hashmap[ltr] += 1

# vs:
for ltr in word:
	if ltr not in hashmap:
		hashmap[ltr] = 0
	
	hashmap[ltr] += 1
```


Backtracking: 
- it's always better to have the ret array outside of the helper function because it's more efficient (appending to a list and passing it in as an argument copies the list)

eg. 
```python
 def combinationSum2(self, candidates: List[int], target: int) -> List[List[int]]:
        ret = []
        current_path = []

		def helper(start_idx: int, cur_sum: int) -> None:
			.
			.
			. 

			# and then just append and pop each time
			current_path.append(candidates[i])
			helper(i + 1, cur_sum + candidates[i], current_path)
			current_path.pop()
```
