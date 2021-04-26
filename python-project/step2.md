We will test  our  code with Pytest which is a ... 

## Install pytest
`python -m pip install pytest`{{execute}}

## Set up our first test
Let's create a file with the code of binary search

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

Great! The test passed since 2 is at index 0 in the array.

<pre class="file" data-filename="search/test_bs.py" data-target="append">

def test_findtwo():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 5
    result = bs(arr, 0, len(arr)-1, x)
    assert result == 0
</pre>

Run the test:
`pytest`{{execute}}

This test fails since 5 is not in the array and we asserted it to be at index 0. Let's change that! 

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

Run the test and make sure it doesn't  fail:
`pytest`{{execute}}