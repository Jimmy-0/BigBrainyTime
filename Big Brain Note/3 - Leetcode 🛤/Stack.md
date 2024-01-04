# 20. Valid Parentheses
- use stack to make sure the sequence is matched
- use hashmap to make sure the opened one can offset the closed one
TIME : O(N) / SPACE O(N)



# 155. Min Stack
- Use a temp stack to store and keep track of the minimum value
	- only store the value if it is smaller.
TIME : O(N) / SPACE O(N)

# 22. Generate Parentheses
- Backtracking 
	- number of open VS number of close 
TIME : O(n) /  SPACE : O(n) or O(2n)

# 739. Daily Temperature
- using stack to hold the temperatures that haven't have the res
- using `while` to make sure that the previous res is taken care
	- 回頭清算
TIME : O(N) / SPACE : O(N)

# Car Fleet
- For each position, calculate the time when the car reach the destination.
- Determine whether it will be merged to the fleet or not.
	- if it will create its own fleet then it will stay in the stack
	- Otherwise it will be merged
- 分兩派，比他快就合併 / 比他慢就會造成新的fleet. 