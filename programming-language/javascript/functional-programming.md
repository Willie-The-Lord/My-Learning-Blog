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

__

####

\
\
