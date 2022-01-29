---
title: 'Plugins & 3rd Party Scripts'
---

Kavita supports the ability to integrate or interact with 3rd party scripts via the Plugin API (WIP). Currently, the API allows authenticating with a user API key and getting a JWT Token back. This will give access to any API the user could call if using the UI authenticated. The plugin API is a planned feature of Kavita, but not fully built out. 

### API Documentation
To view Kavita's API documentation, you will need to build Kavita on your local machine then browse to Swagger UI at http://localhost:5000/swagger/. Kavita uses JWT for authentication and thus you must attach your JWT key to Swagger to test against your local instance. 

You can get your JWT by opening dev tools on a browser you have authenticated against and getting this key "kavita-user" from local storage. This will have a token key within it. Use "Bearer TOKEN_KEY" to authenticate. This must be on all APIs for Kavita to respond.

