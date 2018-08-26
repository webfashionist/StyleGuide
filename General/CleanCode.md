# Write clean code 

## 1. Use descriptive names

The name of the function, variable and classes should instantly be recognizable.

**Bad examples:**

- A variable named `dxy`
- `CalcTan()`

**Good examples:**

- A variable named `seconds`
- `CalculateTangent()`

Using function names like `getVariable()` shouldn't be named `fetchVariable()` somewhere else (and vice-versa) if the functionality is the same.
Different uses would be: `getVariable()` loads the variable from within a class variable, `fetchVariables()` loads the value from the database - in this case the functionality is different and naming the function differently makes more sense.

## 2. Give each class / function a single purpose

Functions should not be several hundreds of lines long, instead it should be broken into different functions.
This allows not only to have a more readable code, but also to reuse existing code more easily.

In practice, a complex calculation like `GetCreditScore()` may need to be broken into several helper functions like `GetCreditReports()`, `ApplyCreditHistoryAge()`, and `FilterOutstandingMarks()`.


## 3. Delete unnecessary code

Over time, old and commented code will be all over the project files - just in case it could ever be reused, checked or reused.
While it may be useful the first few days or weeks after the new code has been implemented, it should be removed soon after that, as it makes the code more difficult to read and the code around the commented code will evolve and might even change completely from the initial code written.

If the code should still be kept for "backup" reasons or to lookup the old code, you should use `git` - if you aren't already.


## 4. Readability

One-liners of code can be clever, take up less space on the screen, but they are harder to understand and debug.

Always optimize code for the next person who’s going to read it, because in all likelihood that next person is actually going to be YOU and there’s nothing more shameful than being unable to read or understand your own cleverness.


## 5. Consistent code style

Keep the same code style throughout your project - if you’re going to use `camelCaseNaming` for variables, don't use `underscore_naming` somewhere else.
Some languages even have language-wide style guides that you may want to follow.

## 6. Write good comments

Comments should explain WHY a piece of code exists rather than WHAT it actually does. 
The code should be self-explanatory as to what it does - adding that information to the comments would make them way larger than needed.

They can as well include warnings, if removing or changing the function could break other functions or features within the project.

PHPDocs, JSDocs and any similar comments should be added for every function, as they describe not only the parameters, but also their data type (integer, string, array, ...) and additional comments can still be added to describe the function and/or the parameters.

## 7. Database connections

In case you're working with database connection (e.g. MySQL, SQLite) you should only open one SQL connection per database for each request.
This doesn't only improve the performance and loading speed of your project, it might as well simplify the understanding as of how the connections are handled and where they are saved/cached or created.
