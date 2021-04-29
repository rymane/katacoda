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

Great! The test passed. If we make a test that is searching for a number that is not included in the array, 
still asserting the result to be 0, it should fail. Try it:

Click *Copy to Editor*.

<pre class="file" data-filename="search/test_bs.py" data-target="append">

def test_findtwo():
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

def test_findtwo():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 5
    result = bs(arr, 0, len(arr)-1, x)
    assert result == -1
</pre>

Run the test and make sure it does not fail:

`pytest`{{execute}}

These test are set up to succeed and fail since we *know* that the code is correct, 
but what we usually want to test is *if* the code is correct. Feel free to change some parts in 
the binarySearch file and run the tests to see if the change made the tests fail or not. 
