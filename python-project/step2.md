It is time to test the code to see that it works correctly and actually does what we want it to.
We will test our code with [pytest](https://docs.pytest.org/en/6.2.x/) which is a python framework used to write unit test easily.

## Install pytest
`python -m pip install pytest`{{execute}}

## Set up our first test
Let's write a test that creates an array and calls binary search to find number 2, 
which is at index 0. We then assert the result to be 0 since that's what we expect the results to be in order for the code to behave correctly.  

*Click copy to Editor to create the file.*
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

Great! The test passed. If we make a test that is searching for a number not in the array, 
still asserting the result to be 0 it should fail. Try it:

*Click copy to Editor to create the file.*

<pre class="file" data-filename="search/test_bs.py" data-target="append">

def test_findtwo():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 5
    result = bs(arr, 0, len(arr)-1, x)
    assert result == 0
</pre>

Run the test:
`pytest`{{execute}}

Exactly, this test fails since 5 is not in the array, and we asserted it to be at index 0. Let's change that! 

*Click copy to editor to create the file.*

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

Run the test and make sure it doesn't fail:

`pytest`{{execute}}

These test are set up to succeed and fail since we *know* that the code is correct, 
but what we usualy want to test is *if* the code is correct. Feel free to change some parts in 
the binarySearch file and run the tests to see if the change made the tests fail or not. 
