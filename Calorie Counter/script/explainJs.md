# Variable Declarations
```js
const calorieCounter = document.getElementById("calorie-counter");
const budgetNumberInput = document.getElementById("budget");
const entryDropdown = document.getElementById("entry-dropdown");
const addEntryButton = document.getElementById("add-entry");
const clearButton = document.getElementById("clear");
const output = document.getElementById("output");
let isError = false;

```
- Grabs key DOM elements by their IDs (the form, inputs, buttons, etc.).

- isError is a flag used to stop calculations if the user types an invalid input.

# Utility Functions

```js
function cleanInputString(str) {
  const regex = /[+-\s]/g;
  return str.replace(regex, "");
}
```
- Declares a function named `cleanInputString` that takes one parameter `str`.

`const regex = /[+-\s]/g;`
- Creates a regular expression and stores it in `regex`
- `/[ ... ]/` is a `character class` — it matches any one of the characters inside.
- The `g` flag means `global` — match every occurrence, not just the first.
  
### Note: `\s` matches any whitespace character (space, tab, newline)
#### Small Note: to avoid any possible ambiguity about - inside a class, some people place the hyphen first `(/[-+\s]/g)` or escape it `(/[+\-\s]/g)`. Either works; `[-+\s]` is a bit clearer that - is literal.

`return str.replace(regex, "");`
- Uses `String.prototype.replace()` to remove all matches of the regex by replacing them with the empty string `""`.

- Because the regex has the g flag, every `+, - and whitespace` in str will be removed.

- `replace()` does not mutate the original string — it returns a `new cleaned string`.
