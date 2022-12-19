# Ternary Operators

<pre class="language-javascript"><code class="lang-javascript">let isRaining = true
isRaining
  ? console.log('You need a rain coat.')
  : console.log('No need for a rain coat.')
<strong>
</strong><strong>isRaining = false
</strong>isRaining
  ? console.log('You need a rain coat.')
  : console.log('No need for a rain coat.')
  
// OutPut
// You need a rain coat.
// No need for a rain coat.
</code></pre>

<pre class="language-javascript"><code class="lang-javascript">let number = 5
number > 0
  ? console.log(`${number} is a positive number`)
  : console.log(`${number} is a negative number`)
<strong>
</strong><strong>number = -5
</strong>number > 0
  ? console.log(`${number} is a positive number`)
  : console.log(`${number} is a negative number`)

// OutPut
// 5 is a positive number
// -5 is a negative number
</code></pre>
