It is now time to test the code to see that it works correctly and actually does what we want it to.
We will test our code with [PyTest](https://docs.pytest.org/en/6.2.x/) which is a Python framework used to write unit test easily.

## Install PyTest
`python -m pip install pytest`{{execute}}

## Set up our first test
Write a test that creates an array and calls binary search to find number 2, 
which is at index 0. Assert the result to be 0 since that is what we expect the results to be in order for the code to behave correctly.  

Click *Copy to Editor* to create the file.
<pre class="file" data-filename="search/test_bs.py" data-target="replace">
from binarySearch import *

def test_findtwo():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 2
    result = bs(arr, 0, len(arr)-1, x)
    assert result  == 0
</pre>

Run the test:
`pytest`{{execute}}

Great! The test passed. As you can see, the file name begins with "test" and the test case has a function name starting
with  "test_" as well, following the naming convention we discussed in the introduction. Without this, PyTest would not find
and execute the tests. 

## Tests named wrong
See what happens if "test_" is removed from the test case:

Click *Copy to Editor* to create the file.
<pre class="file" data-filename="search/test_bs.py" data-target="replace">
from binarySearch import *

def findtwo():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 2
    result = bs(arr, 0, len(arr)-1, x)
    assert result  == 0
</pre>

Run the test:
`pytest`{{execute}}

As you can see, no tests ran since PyTest had problem finding it. 

## Failing test
If we now make a test that is searching for a number that is not included in the array, 
still asserting the result to be 0, it should fail. Try it:

Click *Copy to Editor*.

<pre class="file" data-filename="search/test_bs.py" data-target="append">

def test_findfive():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 5
    result = bs(arr, 0, len(arr)-1, x)
    assert result == 0
</pre>

Run the test:
`pytest`{{execute}}

As expected, the test fails since 5 is not included in the array, and we asserted it to be at index 0. 

Click *Copy to Editor* to change that!

<pre class="file" data-filename="search/test_bs.py" data-target="replace">
from binarySearch import *

def test_findtwo():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 2
    result = bs(arr, 0, len(arr)-1, x)
    assert result  == 0

def test_findfive():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 5
    result = bs(arr, 0, len(arr)-1, x)
    assert result == -1
</pre>

Run the test and make sure it does not fail:
`pytest`{{execute}}

## Tests with error in binary search

The previous tests were set up to succeed and fail since we *know* that the code is correct, 
but what we usually want to test is *if* the code is correct. For example, if we accidentally wrote "<=" instead of 
">=" in the first if statement, the algorithm would not search correctly. The first test should fail and indicate that 
something is wrong in the code. Try it:

Click *Copy to Editor* to create the file.
<pre class="file" data-filename="search/binarySearchError.py" data-target="replace">
def bs (arr, l, r, x):

	# Check base case
	if r <= l:

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

Click *Copy to Editor* to add test cases. 

<pre class="file" data-filename="search/test_bsError.py" data-target="replace">
from binarySearchError import *

def test_findtwoError():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 2
    result = bs(arr, 0, len(arr)-1, x)
    assert result  == 0

def test_findfiveError():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 5
    result = bs(arr, 0, len(arr)-1, x)
    assert result == -1
</pre>

`python3 binarySearchError.py && pytest`{{execute}}
As you see, 3 tests succeeds, but the one named **test_findtwoError** fails, indicating that something is wrong in the code binarySearchError.


Feel free to change some parts in the binarySearch file and run the tests to see if the change made the tests fail or not.

