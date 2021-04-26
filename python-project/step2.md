We will test  our  code with Pytest which is a ... 

## Install pytest
`python -m pip install pytest`{{execute}}

## Set up our first test
Let's create a file with the code of binary search

<pre class="file" data-filename="search/test_bs.py" data-target="replace">
from binarySearch import bs

def test_findtwo():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 2
    result = bs(arr, 0, len(arr)-1, x)
    assert result  == 0
</pre>

Run the test:
`pytest`{{execute}}

<pre class="file" data-filename="search/test_bs.py" data-target="append">

def test_findtwo():
    arr = [ 2, 3, 4, 10, 40 ]
    x = 5
    result = bs(arr, 0, len(arr)-1, x)
    assert result == 0
</pre>

Run the test:
`pytest`{{execute}}


