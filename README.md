#connect-domains

Parse req.headers.host into a heiarchy of domains and sub-domains populating the 'req.domains' object.


## Example

```js
var express = require('express');
var app = express();
// ...
app.use(require('connect-domains')("example.com"));
app.use(function(req,res){
    //when visiting "www.sub1.example.com"
    console.log(req.domains[0]);//"example.com"
    console.log(req.domains[1]);//"sub1"
    console.log(req.domains[2]);//"www"
})
app.listen(8080);
```

