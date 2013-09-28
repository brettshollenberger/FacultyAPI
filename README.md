# FacultyAPI

FacultyAPI creates a simple, RESTful API for MEAN stack apps. 

#### Use:

`npm install faculty-api` or in your package.json `"faculty-api":"~0.0.1"`

Create a Mongoose model, and export it to your backend `app.js`.

A basic use case is illustrated below:

```javascript
var express    = require('express');
var app        = module.exports = express();
var db         = require('./../mongooseModels');
var app        = module.exports = express();
var facultyApi = require('faculty-api');

facultyApi.addResource({
  app: app,
  prefix: 'api',
  resourceName: 'users',
  table: db.user
});
```

The only non-required option is the URL prefix, which defaults to api if you don't specify one. 

In the example above, the URLs established are located at `/api/users/:id`, and include an additional route, `/api/users/schema` in case you want access to schema attributes for things like front-end validations.
