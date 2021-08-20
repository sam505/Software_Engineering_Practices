# Software_Engineering_Practices

## Version Control

Step 1: Andrew commits his changes to the documentation branch, switches to the development branch, and pulls down the latest changes from the cloud on this development branch, including the change I merged previously for the friends group feature.
Commit the changes on the documentation branch
git commit -m "standardized all docstrings in process.py"

Switch to the develop branch

`git checkout develop`

Pull the latest changes on the develop branch down

`git pull`

Step 2: Andrew merges his documentation branch into the develop branch on his local repository, and then pushes his changes up to update the develop branch on the remote repository.
Merge the documentation branch into the develop branch

`git merge --no-ff documentation`

Push the changes up to the remote repository

`git push origin develop`

Step 3: After the team reviews your work and Andrew's work, they merge the updates from the development branch into the master branch. Then, they push the changes to the master branch on the remote repository. These changes are now in production.
Merge the develop branch into the master branch

`git merge --no-ff develop`

Push the changes up to the remote repository

`git push origin master`

## Model Vesrsioning
- [Version Control ML Model](https://towardsdatascience.com/version-control-ml-model-4adb2db5f87c)
- [How to version control your production machine learning models](https://algorithmia.com/blog/how-to-version-control-your-production-machine-learning-models)

## Code Review
### Questions to consider when doing a code review:
- #### Is the code clean and modular?
  - Can I understand the code easily?
  - Does it use meaningful names and whitespace? 
  - Is there duplicated code? 
  - Can I provide another layer of abstraction? 
  - Is each function and module necessary? 
  - Is each function or module too long?


- #### Is the code efficient? 
  - Are there loops or other steps I can vectorize?
  - Can I use better data structures to optimize any steps?
  - Can I shorten the number of calculations needed for any steps?
  - Can I use generators or multiprocessing to optimize any steps?


- #### Is the documentation effective?
  - Are inline comments concise and meaningful?
  - Is there complex code that's missing documentation?
  - Do functions use effective docstrings?
  - Is the necessary project documentation provided?


- #### Is the code well tested?
  - Does the code high test coverage?
  - Do tests check for interesting cases?
  - Are the tests readable?
  - Can the tests be made more efficient?


- #### Is the logging effective?
  - Are log messages clear, concise, and professional?
  - Do they include all relevant and useful information?
  - Do they use the appropriate logging level?

### Tips
- Use a code linter ([pylint](https://www.pylint.org/))
- Explain issues and make suggestions
- Keep your comments objective
- Provide code examples
```python
first_names = []
last_names = []

for name in enumerate(df.name):
    first, last = name.split(' ')
    first_names.append(first)
    last_names.append(last)

df['first_name'] = first_names
df['last_names'] = last_names
```

``
BAD: You can do this all in one step by using the pandas str.split method.
``

``
GOOD: We can actually simplify this step to the line below using the pandas str.split method. 
Found this on this stack overflow post: https://stackoverflow.com/questions/14745022/how-to-split-a-column-into-two-columns
``

```python
df['first_name'], df['last_name'] = df['name'].str.split(' ', 1).str
```