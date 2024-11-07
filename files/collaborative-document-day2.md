![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document

2024-11-05 HybridLabs - Good Practices in Research Software Development - **Day 2**

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: [link](https://edu.nl/n43fa)

Collaborative Document day 1: [link](https://edu.nl/3wx8g)

Collaborative Document day 2: [link](https://edu.nl/n43fa)


##  🫱🏽‍🫲🏻 Code of Conduct

Participants are expected to follow these guidelines:
* Use welcoming and inclusive language.
* Be respectful of different viewpoints and experiences.
* Gracefully accept constructive criticism.
* Focus on what is best for the community.
* Show courtesy and respect towards other community members.
 
## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: [creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).

## 🙋Getting help

To ask a question, just raise your hand.

If you need help from a helper, place a pink post-it note on your laptop lid. A helper will come to assist you as soon as possible.

## 🖥 Workshop website

[link](https://esciencecenter-digital-skills.github.io/2024-11-05-ds-cr-Hybridlabs/)

🛠 Setup

[link](https://esciencecenter-digital-skills.github.io/2024-11-05-ds-cr-Hybridlabs/#setup)

## 👩‍🏫👩‍💻🎓 Instructors

Francesco Nattino, Djura Smits

## 🧑‍🙋 Helpers

Thijs van Lankveld, Lucas Esclapez  

# 🗓️ Agenda

| Time  | Topic                             |
|-------|-----------------------------------|
| 09:30	| Modular Code Development          |
| 10:30	| Morning break                     |
| 11:00	| Code Documentation                |
| 12:00	| Lunch break                       |
| 13:00	| Testing                           |
| 15:00	| Afternoon break                   |
| 15:30	| Continuous Integration            |
| 16:45	| Wrap-up                           |
| 17:00	| END & Drinks                      |

## 🏢 Location logistics
* Coffee and toilets are in the hallway, just outside of the classroom.
* If you leave the building, 
  be sure to be accompanied by someone from the escience center to let you back in through the groundfloor door
* For access to this floor you might need to ring the doorbell so someone can let you in
* In case of an emergency, you can exit our floor using the main staircase.
  Or follow green light signs at the ceiling to the emergency staircase.
* **Wifi**: Eduroam should work. Otherwise use the 'matrixbuilding' network, password should be printed out and available somewhere in the room.

## 🎓 Certificate of attendance

If you attend the full workshop you can request a certificate of attendance by emailing to training@esciencecenter.nl.
Please request your certificate within 8 months after the workshop, as we will delete all personal identifyable information after this period.

## 🧠 Collaborative Notes

Collaboration with GitHub (demonstration by Djura)

 - Issues tab is used to keep track of ongoing wishlist, report a bug, ...
 - When creating a new issues, select a short, descriptive title and then write up a small description
 - Users can be tagged in the issue description (using @<github_name>) and they will get notified (by email, directly on Github, ...)
 - When deciding to work on an issue, you can assign it to yourself (top-right) to notify others that the issue will be resolved
- To start working on the issue, you will have to clone it
  ```(bash)
  git clone git@github.com:hybridlabs-nl/collaborative-version-control-demo.git
  ```
  > This will create a new local directory (`collaborative-version-control-demo/`) with the local copy of the repository.
- Create a new branch.
  ```(bash)
  git switch -c add-numbers
  ```
- Create a new python script to handle the task
  ```(bash)
  nano calculate.py
  ```
  in the file:
  ```(bash)
  def add(a, b):
      return a - b
  ```
  Write the file (`Ctrl-O`) and exit (`Ctrl-X`).
  ```(bash)
  git status
  ```
  > You can confirm that there is a new file in the new (`add-numbers`) branch
  Push the local changes to the remote repository.
  ```(bash)
  git push --set-upstream origin add-numbers
  ```
  > The message should state that there's a new branch created.
- Create a pull request (on GitHub) to review the work and integrate the work into the main branch.
  If you go to GitHub straight after pushing a new branch, GitHub will suggest creating a pull request for this branch.
- Your colleague can now review the pull request, comment, or require/suggest further changes to correct the work, or to fix any issues when integrating the work.
  The pull request lists all the changes that would be applied when integrating the work.
  You can add comments to specific lines, or multiple lines. While reviewing, you can also suggest changes:
  ```
      ```suggestion
          return a + b
      ```
  ```
- The creator of the pull request can now process the review, possibly committing any suggested changes.
- Like other review processes, the creater and reviewer can go back and forther commenting and/or suggesting changes, until the reviewer is approves the pull request.
- After the pull request is approved, it can be merged and the issue can be closed.

There can be situations where you are not a registered collaborator of a repository.
In this case, you may still be able to contribute to this repository, by creating a fork.
- Create a new fork on GitHub by using the Fork button from the main repository. This creates a remote copy of the repository, where you do have edit rights.
- To make any changes, you will have to clone your fork to create a local copy of the fork, similar to how you would clone the original repository.
- To make any of the changes to your fork have effect on the original repository, you will have to create a pull request on that original repository, requesting to pull your fork into the original.


[Documentation](https://esciencecenter-digital-skills.github.io/digital-skills-slides/modules/good-practices-lesson/documentation-slides)

- There are different types of documentation, which you expect to find in different places. For example:
  - Comments describing what's happening in the code itself
  - API documentation describing what a function is going to do, what input to provide and what output to expect.
  - Usage examples, how to use the software, usually in a readme file.
  - Installation instructions, how to set up the software to be able to start running it, usually in a readme file.

- What should be in a readme file?
  - Name of the software
  - Short description
  - Usage examples
  - Installation instructions
  - Licence covering the software
  - Who owns the software
  - Who contributed to the software
  - How to contribute

 - Adding documentation is not always required, e.g. when the following items are already present:
    - Self-explanatory code
    - Well-named variables

 - Using docstrings: differs from plain comments in that they can be refered to/used outside of the code. Most IDE automatically picks up docstrings to provide information to the developer (i.e. hovering on a function name).

 - API generation tools:
     - Sphinx: create nicely-formatted HTML from .md/.rst files
     - Github pages: can be used to host the HTML generated from Sphinx
     - Documentation can be build automatically using Github functionalities (Github actions). To do so: you can create a hidden folder ```.github``` in your repository and add YAML (.yml) files that github will automatically detect. There is an [example](https://github.com/esciencecenter-digital-skills/good-practices-documentation-example/blob/main/.github/workflows/documentation.yml) of YAML file for building documentation using Sphinx online.

 - Key take-away:
     - Documentation does not replace descriptive naming
     - Different types of documentation:
         - Readable code
         - In-code comments
         - Docstrings
         - README file
         - Tutorials
     - Comments describe the why for the code, not simply describe the code (especially if the code is self-explanatory)
     - Docstrings can be used in place of comments at the top of functions, they will be picked up by IDE and automatic API documentation generators

[Testing](https://esciencecenter-digital-skills.github.io/digital-skills-slides/modules/good-practices-lesson/testing-slides)

- Introduction:
    - Humans write and use the code, so mistakes will happen.
    - More complex code leads to increasing difficulty in keeping track of everything
    - Build safeguards (more code) to prevent or catch problems:
        - Throw exceptions
        - Log results/actions
        - Write tests

Type-along exercices:

In your workshop directory.
Activate your conda environment, to enable ```pytest```:
```
conda activate coderefinery
```
Create a Python file with a function and then a test for that function. Using your favorite editor, for example ```nano```:
```
nano calculate.py
```
and define a simple ```add``` function:
```python
def add(a, b):
    return a + b
```

In the same file, now add a couple of test functions. Test functions need to begin with ```test_```:
```python
def test_add_numbers():
    assert add(2,3) == 5
```
The ```assert``` is special Python assessing that the statement provide is True. Let's now use ```pytest``` to run the test function:
```
pytest calculate.py
```
```pytest``` successfully complete, explicitly reporting that 1 test was successful.

Now add a function to add strings in the same file:
```python
def test_add_strings():
    assert add("djura", "smits") == "djurasmits"
```
and run ```pytest``` again:
```
pytest calculate.py
```
```pytest``` automatically picks up the second test we implemented and report that 2 tests were successful.

If at any point in the future, you change the ```add``` function, say:
```git
-- return a + b
++ return a - b
```
and re-run ```pytest```, both tests will fail.


FizzBuzz test solution by Djura.
Let's first write all the tests with an empty ```fizzbuzz``` function:
```python
import pytest

def fizzbuzz(n):
    pass

def test_fail_below_zero():
    with pytest.raises(Exception):
        fizzbuzz(-1)
        
def test_fail_zero():
    with pytest.raises(Exception):
        fizzbuzz(0)
        
def test_multiple_3():
    assert fizzbuzz(9) == "fizz"
    
def test_multiple_5():
    assert fizzbuzz(10) == "buzz"
    
def test_multiple_3_5():
    assert fizzbuzz(15) == "fizzbuzz"
    
def test_other_numbers():
    assert fizzbuzz(2) == 2  
```

Now run ```pytest```:
```
pytest fizzbuzz.py
```
All the tests are failing, which is expected at this point.

Let's now implement the ```fizzbuzz``` function:
```python
def fizzbuzz(n):
    if n <= 0:
        raise Exception()
    elif n % 3 == 0 and n % 5 == 0:
        return "fizzbuzz"
    elif n % 3 == 0:
        return "fizz"
    elif n % 5 == 0:
        return "buzz"
    else:
        return n
```
Re-run ```pytest```. All the tests should now pass. What would have happened if you had implemented the first ```elif``` statement (```elif n % 3 == 0 and n % 5 == 0```) as the last one in the ```fizzbuzz``` function ?

[Continuous Integration](https://esciencecenter-digital-skills.github.io/digital-skills-slides/modules/good-practices-lesson/ci-slides)

 - Continuous integration can be triggered by any push to the repository, automating tests, documentation build, ...
 - Can be designed to test the code on different platforms: Windows, Linux, Mac, ...; or diferent version of the software stack (different Python version, ...)
 - Automate deployments: upload your package to PyPi (for Python packages), build Sphinx documentation and update the Github page, ...
 - Run some code analysis: static analysis, code style, coverage, ...

Hands-on

### Exercises

#### Exercise: Working as an external contributor (in pairs)

- PERSON A: Create an issue in Person B's repository
- PERSON A: Fork the repository to their own (= Person A's) account
- PERSON A: Clone the repository, make changes, push them back to the fork
- PERSON A: Submit a Pull Request from the fork to the original repository
- PERSON B: Make a change in the original repository in the same place as person A's proposed changes
- PERSON A: Solve the merge conflict in the Pull Request
- PERSON B: Review/Approve the Pull Request
- PERSON B: merge the Pull Request


#### Exercise: Modularity 

Carefully review the following code snippet:

```python
def convert_temperature(temperature, unit):
    if unit == "F":
        # Convert Fahrenheit to Celsius
        celsius = (temperature - 32) * (5 / 9)
        if celsius < -273.15:
            # Invalid temperature, below absolute zero
            return "Invalid temperature"
        else:
            # Convert Celsius to Kelvin
            kelvin = celsius + 273.15
            if kelvin < 0:
                # Invalid temperature, below absolute zero
                return "Invalid temperature"
            else:
                fahrenheit = (celsius * (9 / 5)) + 32
                if fahrenheit < -459.67:
                    # Invalid temperature, below absolute zero
                    return "Invalid temperature"
                else:
                    return celsius, kelvin
    elif unit == "C":
        # Convert Celsius to Fahrenheit
        fahrenheit = (temperature * (9 / 5)) + 32
        if fahrenheit < -459.67:
            # Invalid temperature, below absolute zero
            return "Invalid temperature"
        else:
            # Convert Celsius to Kelvin
            kelvin = temperature + 273.15
            if kelvin < 0:
                # Invalid temperature, below absolute zero
                return "Invalid temperature"
            else:
                return fahrenheit, kelvin
    elif unit == "K":
        # Convert Kelvin to Celsius
        celsius = temperature - 273.15
        if celsius < -273.15:
            # Invalid temperature, below absolute zero
            return "Invalid temperature"
        else:
            # Convert Celsius to Fahrenheit
            fahrenheit = (celsius * (9 / 5)) + 32
            if fahrenheit < -459.67:
                # Invalid temperature, below absolute zero
                return "Invalid temperature"
            else:
                return celsius, fahrenheit
    else:
        return "Invalid unit"
```

Refactor the code by extracting functions without altering its functionality.

- What functions did you create?
- What strategies did you use to identify them?

Share your answers in the collaborative document.

#### Test-Driven Development: FizzBuzz Function (15 min)

The function `fizz_buzz()` takes an integer argument and returns it, BUT:

- Fails on zero or negative numbers.
- Instead returns "Fizz" on multiples of 3.
- Instead returns "Buzz" on multiples of 5.
- Instead returns "FizzBuzz" on multiples of 3 and 5.

Create an empty function `fizz_buzz()` and go through the conditions listed above, one by one:

1. Write a test for the condition.
2. Edit the `fizz_buzz()` function until the test passes.

Then discuss together the different solutions.

def test_fizzbuzz():
    for i in range(1,6):
        assert fizzbuzz(3*i) == 'fizz'
    for i in range(1,4):
        assert fizzbuzz(5*i) == 'buzz'
    assert fizzbuzz(15) == 'fizzbuzz'
    assert(0) == 'fail'
    

#### Exercise: Collaborative Integration

[Collaborative CI Exercise](https://esciencecenter-digital-skills.github.io/good-practices-lesson/4-ci.html#full-cycle-collaborative-workflow)


## 📚 Resources

https://www.sphinx-doc.org/en/master/
https://pages.github.com/