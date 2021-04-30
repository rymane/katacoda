## Introduction
Welcome to this tutorial about continuous integration for a Python project.
In this tutorial, we will build a simple [Python](https://www.python.org) project and use [PyTest](https://docs.pytest.org/en/6.2.x/) 
which is a python framework used to easily write unit tests. In the last step we will learn how to integrate [Travis CI](https://www.travis-ci.com), which is
a service for continuous integrations used to continuously build and test code on GitHub or Bitbucket.

### Testing
Unittest is another alternative for testing Python projects and has been built into the Python standard library for some time. PyTest supports execution of unittest test cases and has some 
more advantages, which is why it is used in this tutorial. With PyTest, you can utilize the built-in assert statement instead 
of having to use special methods like self.assert*(), which is needed with unittest. PyTest supports the functionality to filter test cases and 
has the ability to rerun tests from the last failing test. Moreover, it exists hundreds of plugins for PyTest to extend
the functionality. PyTest is also very easy to use. There is no need to import PyTest for it to work, as long as every test file starts 
or ends with "test" and every test case starts with "test_", PyTest will find and run the test cases. 

### Goal of this tutorial
By the end of this tutorial you will have:

- Created a simple Python project implementing the binary search algorithm.
- Created unit tests with PyTest.
- Connect GitHub to Travis CI and learned how to build and test the project automatically.