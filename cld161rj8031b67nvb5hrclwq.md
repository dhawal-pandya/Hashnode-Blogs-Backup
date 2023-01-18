# Demystifying CORS

Unlike MERS or SARS, this one is actually meant to protect you.

CORS (Cross-Origin Resource Sharing) is a security feature implemented by web browsers that block web pages from making requests to a different domain than the one that served the web page. This is done to prevent malicious websites from making unauthorized requests on behalf of the user.

For example, if a web page served from "example.com" makes a request to "api.example.com", the browser will block the request because the domains are different. This is because web pages are not allowed to make requests to a different domain for security reasons.

However, some web applications need to make cross-origin requests. For example, a web application that is served from "example.com" might need to make requests to an API that is served from "api.example.com". In this case, the web application can use CORS to make cross-origin requests.

To enable CORS for a specific resource, the server that hosts the resource, the thing that the fetcher wants, must include the appropriate CORS headers in the HTTP response.

The most important headers are:

**Access-Control-Allow-Origin**:

This header specifies the origin or origins that are allowed to make cross-origin requests to the resource. The value can be set to "\*" to allow any origin or a specific origin.

**Access-Control-Allow-Methods**:

This header specifies the allowed methods for the resource. For example, if the value is set to "GET, POST", then only GET and POST requests are allowed.

**Access-Control-Allow-Headers**:

This header specifies the allowed headers for the resource. For example, if the value is set to "Content-Type", then only requests that include the "Content-Type" header are allowed.

**Access-Control-Allow-Credentials**:

This header is used to allow or disallow the use of credentials in cross-origin requests. The value of this header is a boolean indicating whether or not the resource can be accessed with credentials.

So on your NodeJS Server, you need to include these to allow access to your resources to everyone, using the "\*":

```javascript
const express = require('express')

const app = express();
app.use((req, res, next) => {
    res.header("Access-Control-Allow-Origin", "*"); 
    res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
    next();
});
app.get('/', (req, res) => {
    res.send('Hello World!')
    }}
app.listen(3000, () => {
    console.log('Someone is always listening, better tape the webcam!')
});
```

Here, my server is using the express framework and the `app.use` middleware is used to set the headers on every request.

CORS can also be enabled on the client-side by adding the appropriate headers to the request. For example, in an XMLHttpRequest, you can set the withCredentials property to true to allow the use of credentials in cross-origin requests.

This is what the CORS plugins do actually.

It is important to note that CORS is a security feature and should be used with caution. It is generally recommended to use specific origins rather than allowing any origin. And also, CORS headers should only be set on resources that need to be accessed from a different domain, and not on resources that don't need to be accessed from a different domain.

Hope I helped and not made you question your life choices by clicking this post.