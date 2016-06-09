# Week 2: Javascript and the DOM

Following the example of sorting, which we did in class, we'll finish wiring up the functionality of the page.

## Task 1 - Filter
Add a set of buttons that filter the data. If you don't have a categorical variable in your data, you might fake one by, for example, creating filters based on the first letter of a variable, i.e. all the names starting with 'A'. You'll probably need the [Array.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) method.

```js
var arr = [0, 1, 2, 3, 4, 5]

var filtered = arr.filter(function (d) { return d > 2; })
// [3, 4, 5]
```

## Task 2 - Pagination

Instead of showing all of the rows on a single page, let's break them up into smaller pages of maybe 15 or 20 rows each. We added a `page` property to the options object in class, setting its initial value to `0`. The next/previous buttons should increment/decrement this value. In order to select the rows of data for the given page, you'll probably need the [Array.slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) method.

```js
var arr = ['a', 'b', 'c', 'd', 'e', 'f', 'g']

var sliced = arr.slice(1, 5)
// ['b', 'c', 'd', 'e']
```

## Troubleshooting

#### "I'm filtering/slicing, but nothing's happening..."

Remember that unlike Array.sort, which sorts the data in place (also known as "mutating" it), Array.filter and Array.slice return new arrays, leaving the original array untouched. So while the sort operation we did in class could just call `data.sort(...)`, the new operations you're creating will need to assign the returned array back to the `data` variable, replacing the original array. So they might look something like this: `data = data.filter(...)`
