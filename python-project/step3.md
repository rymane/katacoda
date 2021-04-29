Great job! This far we have made a small python project and written unit tests for it.
Now it is time to set up [Travis CI](https://www.travis-ci.com) which is
a service for continuous integrations, used to build and test our code automatically on every push.  

If you have followed along this tutorial in your own repo, you can use it for this step. Otherwise,
you fork the repo by pressing the button right under your profile picture saying "fork".

## Connect Travis with your GitHub
First, you want to connect Travis CI to your GitHub account. 
1. Go to [Travis CI](https://www.travis-ci.com) and select **Sign up with GitHub**
2. Accept the authorization on your screen.
3. Either click *Activate all repositories using GitHub Apps* or go to your profile by pressing
the profile picutre, then click Settings and the green Activate button, and select the repositories you want to use with Travis CI.

## Configure Travis 
In order for Travis CI to work the GutHub repo has to have a file named .travis.yml located in the root of the repository. 
This file will tell travis which language is used together with the desired building and testing environment. If any dependencies has 
to be installed before building the software, this is stated in the .travis.yml file as well. You can read more about the .travis.yml file [here](https://docs.travis-ci.com/user/tutorial/)

First, we add information about what language we are using for the project.
<pre class="file" data-filename="search/.travis.yml" data-target="replace">
language: python
</pre>

We also want to add a script that makes Travis run the tests from the previous step with pytests.
<pre class="file" data-filename="search/.travis.yml" data-target="append">
script: 
  - pytest
</pre>

Since our project is small and don't have any dependencies this is everything needed in the .travis.yml file.
If this file was pushed to GitHub together with binarySearch and the tests, then for every push Travis
would run our code, and the test it automatically with our specified tests. For each commit, Travis will show
a orange dot while the build and tests are running, a green dot if everything succeeded, and a red dot if something failed.


Forking the repo gives you write access so that you can try and test it out.
For example, you can try to ...