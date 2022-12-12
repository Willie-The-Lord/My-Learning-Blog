# @app.route()

The route() function of the Flask class is a decorator, which tells the application which URLpython should call the associated function.

<pre class="language-python"><code class="lang-python"><strong>app.route(rule, options)
</strong></code></pre>

* The rule parameter represents URL binding with the function.
* The options is a list of parameters to be forwarded to the underlying Rule object.

### app.add\_url\_rule()

The add\_url\_rule() function of an application object is also available to bind a URL with a function as in the above example, route() is used.

```python
def hello_world():
   return ‘hello world’
app.add_url_rule(‘/’, ‘hello’, hello_world)
```
