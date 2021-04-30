We begin by setting up a simple Python project. 
We will implement binary search for demonstration purposes.

## Implement Binary search
Create a file with the code of binary search.

Click `Copy to Editor` to create the file.
<pre class="file" data-filename="/binary-search/search/binarySearch.py" data-target="replace">
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

Binary search takes an array, a start, an end and the number to search for as an input. 
It returns the index where the number is found if it exists in the array, otherwise it returns -1. You can read more about binary search [here](https://www.geeksforgeeks.org/binary-search/).

Add your new file to your git repository: `git add search/binarySearch.py`{{execute}}

Commit the changes: `git commit -m "Add binary Search"`{{execute}}
