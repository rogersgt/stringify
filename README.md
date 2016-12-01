# string-bundle

string-bundle takes an html file and renders it into a JavaScript file for exporting as a string template. String-bundle is intended to be used as a straightforward way of using html template files for various JavaScript frameworks (like Vue.js) and libraries with a simple-to-use tool.

`sudo npm install string-bundle -g`

`string-bundle template.html output.js`

Using string-bundle with Vue.js:

### home.html
``` bash
<div class="pageWrapper">
  <h1>Home</h1>
  <h3>{{message}}</h3>
</div>
```

Then create a blank JavaScript file: home.js.

`string-bundle home.html home.js`

### index.js
`const home = require('path/to/home.js');`

``` bash
const homeComponent = new Vue({
  el: '#app',
  template: home,
  data: {
    message: 'hello string-bundle'
  }
});
```


## Advanced

### string-bundle.json
``` bash
{
  "modules": [
    {
      "input": "path/to/template.html",
      "output": "path/to/output.js"
    }
  ]
}
```
Then simply: `string-bundle` will compile all files listed in the "modules" section of the string-bundle.json file.
