Great job! Now it is time to set up Travis CI...
Travis CI is ... about .travis.yml file
## Create yaml file
First, we add information about what language we are using for the project and specify which version
<pre class="file" data-filename="search/.travis.yml" data-target="replace">
language: python
python:
  - "2.7"
  - "3.8"
</pre>

Next, we add some extra requirements. For larger project with a lot of packages to install, you can use a [requirement.txt](länk) file instead.
But right now we will only need pytest so this one line does the job. 
<pre class="file" data-filename="search/.travis.yml" data-target="append">
Pre_install: pip3 install -U pytest
</pre>

Install python 3:
<pre class="file" data-filename="search/.travis.yml" data-target="append">
Install: pip3 install
</pre>

We also want to add a script that makes Travis run the tests from the previous step.
<pre class="file" data-filename="search/.travis.yml" data-target="append">
pre_install:
script: pytest
</pre>