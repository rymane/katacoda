Great job! Now it is time to set up Travis CI...

## Create yaml file
<pre class="file" data-filename="search/.travis.yml" data-target="replace">
language: python
python:
  - "2.7"
  - "3.8"
virtualenv:
  system_site_packages: true
</pre>

<pre class="file" data-filename="search/.travis.yml" data-target="append">
install:
  - pip3 install -r requirements.txt
  - pip3 install 
</pre>

We also want to add a script that makes Travis run the tests from the previous step.
<pre class="file" data-filename="search/.travis.yml" data-target="append">
# command to run tests
script: pytest
</pre>
