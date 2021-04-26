We begin by setting up a simple python project.

## Create the github folder
`mkdir search && cd search && git init`{{execute}}

## Implement python code
Let's create a file with the code of binary search

<pre class="file" data-filename="search/binarySearch.py" data-target="replace">
# implementation from https://www.geeksforgeeks.org/binary-search/

# Returns index of x in arr if present, else -1
def bs (arr, l, r, x):

	# Check base case
	if r >= l:

		mid = l + (r - l) // 2

		# If element is present at the middle itself
		if arr[mid] == x:
			return mid
		
		# If element is smaller than mid, then it
		# can only be present in left subarray
		elif arr[mid] > x:
			return bs(arr, l, mid-1, x)

		# Else the element can only be present
		# in right subarray
		else:
			return bs(arr, mid + 1, r, x)

	else:
		# Element is not present in the array
		return -1
</pre>

Let's run the code:
`python3 bs.py`{{execute}}

Excellent! Now a project is often bigger than this with several files and folders but this is just for demonstration purposes.
Not let's see how be can test our code. 



