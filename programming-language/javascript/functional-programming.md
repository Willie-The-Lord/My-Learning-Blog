# Functional Programming

#### forEach

_forEach_: Iterate an array elements. <mark style="background-color:blue;">We use</mark> <mark style="background-color:blue;"></mark>_<mark style="background-color:blue;">forEach</mark>_ <mark style="background-color:blue;"></mark><mark style="background-color:blue;">only with arrays.</mark> It takes a callback function with elements, index parameter and array itself. The index and the array optional.

```javascript
arr.forEach(function (element, index, arr) {
  console.log(index, element, arr)
})
// The above code can be written using arrow function
arr.forEach((element, index, arr) => {
  console.log(index, element, arr)
})
// The above code can be written using arrow funection and explicit return
arr.forEach((element, index, arr) => console.log(index, element, arr))
```

```javascript
let sum = 0;
const numbers = [1, 2, 3, 4, 5];fav
numbers.forEach(num => console.log(num))
console.log(sum)
// 1
// 2
// 3
// 4
// 5
```

```javascript
let sum = 0;
const numbers = [1, 2, 3, 4, 5];
numbers.forEach(num => sum += num)

console.log(sum)
// 15
```

#### map

_map_: Iterate an array elements and modify the array elements. It takes a callback function with elements, index , array parameter and return a new array.

```javascript
const modifiedArray = arr.map(function (element, index, arr) {
  return element
})
```

<pre class="language-javascript"><code class="lang-javascript">/*Arrow function and explicit return
const modifiedArray = arr.map((element,index) => element);
*/
//Example
const numbers = [1, 2, 3, 4, 5]
const numbersSquare = numbers.map((num) => num * num)

console.log(numbersSquare)
<strong>// [1, 4, 9, 16, 25]
</strong></code></pre>

### filter

_Filter_: Filter out items which full fill filtering conditions and return a new array.

```javascript
const scores = [
  { name: 'Asabeneh', score: 95 },
   { name: 'Lidiya', score: 98 },
  { name: 'Mathias', score: 80 },
  { name: 'Elias', score: 50 },
  { name: 'Martha', score: 85 },
  { name: 'John', score: 100 },
]

const scoresGreaterEighty = scores.filter((score) => score.score > 80)
console.log(scoresGreaterEighty)
```

```javascript
[{name: 'Asabeneh', score: 95}, { name: 'Lidiya', score: 98 },{name: 'Martha', score: 85},{name: 'John', score: 100}]
```

### reduce

_reduce_: Reduce takes a callback function. The call back function takes accumulator, current, and optional initial value as a parameter and returns a single value. It is a good practice to define an initial value for the accumulator value. If we do not specify this parameter, by default accumulator will get array `first value`. If our array is an _empty array_, then `Javascript` will throw an error.

```javascript
const numbers = [1, 2, 3, 4, 5]
const sum = numbers.reduce((acc, cur) => acc + cur, 0)

console.log(sum)
```

```javascript
arr.reduce((acc, cur) => {
  // some operations goes here before returning a value
 return 
}, initialValue)
// 15
```

### every

_every_: Check if all the elements are similar in one aspect. It returns boolean

```javascript
true
```

```javascript
const names = ['Asabeneh', 'Mathias', 'Elias', 'Brook']
const areAllStr = names.every((name) => typeof name === 'string') // Are all strings?

console.log(areAllStr)
```

### find

_find_: Return the first element which satisfies the condition

```javascript
18
```

```javascript
const ages = [24, 22, 25, 32, 35, 18]
const age = ages.find((age) => age < 20)

console.log(age)
```

### sort

_sort_: The sort methods arranges the array elements either ascending or descending order. By default, the _**sort()**_ method sorts values as strings.This works well for string array items but not for numbers. If number values are sorted as strings and it give us wrong result. Sort method modify the original array. It is recommended to copy the original data before you start using _sort_ method.\
\
**Sorting string values**

```javascript
const products = ['Milk', 'Coffee', 'Sugar', 'Honey', 'Apple', 'Carrot']
console.log(products.sort()) // ['Apple', 'Carrot', 'Coffee', 'Honey', 'Milk', 'Sugar']
//Now the original products array  is also sorted
```

**Sorting Numeric values**

As you can see in the example below, 100 came first after sorted in ascending order. Sort converts items to string , since '100' and other numbers compared, 1 which the beginning of the string '100' became the smallest. To avoid this, we use a compare call back function inside the sort method, which return a negative, zero or positive.

```javascript
const numbers = [9.81, 3.14, 100, 37]
// Using sort method to sort number items provide a wrong result. see below
console.log(numbers.sort()) //[100, 3.14, 37, 9.81]
numbers.sort(function (a, b) {
  return a - b
})

console.log(numbers) // [3.14, 9.81, 37, 100]

numbers.sort(function (a, b) {
  return b - a
})
console.log(numbers) //[100, 37, 9.81, 3.14]
```

**Sorting Object Arrays**

Whenever we sort objects in an array, we use the object key to compare. Let us see the example below.

```javascript
objArr.sort(function (a, b) {
  if (a.key < b.key) return -1
  if (a.key > b.key) return 1
  return 0
})

// or

objArr.sort(function (a, b) {
  if (a['key'] < b['key']) return -1
  if (a['key'] > b['key']) return 1
  return 0
})

const users = [
  { name: 'Asabeneh', age: 150 },
  { name: 'Brook', age: 50 },
  { name: 'Eyob', age: 100 },
  { name: 'Elias', age: 22 },
]
users.sort((a, b) => {
  if (a.age < b.age) return -1
  if (a.age > b.age) return 1
  return 0
})
console.log(users) // sorted ascending
// [{…}, {…}, {…}, {…}]
```
