---
title: Misc
---

#### Page overview
Api Documentation<br/>
[Tachiyomi](./tachiyomi)<br/>

<hr style="border:5px solid #4ac694"> </hr>
## Api Documentation
To view Kavita's API documentation, you will need to build Kavita on your local machine then browse to Swagger UI at http://localhost:5000/swagger/. Kavita uses JWT for authentication and thus you must attach your JWT key to Swagger to test against your local instance.

You can get your JWT by opening dev tools on a browser you have authenticated against and getting this key "kavita-user" from local storage. This will have a token key within it. Use "Bearer TOKEN_KEY" to authenticate. This must be on all APIs for Kavita to respond.

<hr style="border:5px solid #4ac694"> </hr>
## Tachiyomi
Kavita does have it's own Tachiyomi extension. 

[Access the guide for Tachiyomi here](./Tachiyomi)