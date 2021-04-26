We begin by setting up a simple python project.

## Create the github folder
`mkdir search`{{execute}}
`cd search`{{execute}}
`git init`{{execute}}

## Implement python code
Let's create a file with the code of binary search

<pre class="file" data-filename="search/binarySearch.py" data-target="replace">
# implementation from https://www.geeksforgeeks.org/binary-search/

# Returns index of x in arr if present, else -1
def binarySearch (arr, l, r, x):

	# Check base case
	if r >= l:

		mid = l + (r - l) // 2

		# If element is present at the middle itself
		if arr[mid] == x:
			return mid
		
		# If element is smaller than mid, then it
		# can only be present in left subarray
		elif arr[mid] > x:
			return binarySearch(arr, l, mid-1, x)

		# Else the element can only be present
		# in right subarray
		else:
			return binarySearch(arr, mid + 1, r, x)

	else:
		# Element is not present in the array
		return -1

# Driver Code
arr = [ 2, 3, 4, 10, 40 ]
x = 10

# Function call
result = binarySearch(arr, 0, len(arr)-1, x)

if result != -1:
    print ("Element is present at index % d" % result)
else:
    print ("Element is not present in array")
</pre>

Let's run the code:
`python3 binary-search.py`{{execute}}

Excellent! Now a project is often bigger than this with several files and folders but this is just for demonstration purposes.
Not let's see how be can test our code. 



