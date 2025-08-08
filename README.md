# HTTP-HTTP2-HTTPS
- HTTP module:
- This is the basic Node.js model for creating HTTP servers and is most commonly used for simple applications
- It supports HTTP/1.1 (the older version of the protocol)
- You can use it if you want to build an API or an unencrypted website (without HTTPS)
- Connections are not secure (without encryption)

const http = require('http');

const server = http.createServer((req, res) => {

res.end('we are using HTTP');

});

server.listen(3000);

-----------------------------------------
- HTTP2 module:
- We use it for creating HTTP/2 servers and clients (encrypted and unencrypted)
- Supports the modern HTTP/2 protocol
- Can be used with or without SSL/TLS encryption
- Provides advanced features to improve performance

const http2 = require('http2');

const server = http2.createServer((req, res) => {

  res.end('we are using HTTP2');

});

server.listen(3000);

-----------------------------------------
- HTTPS module:
- Built on the HTTP module but with TLS/SSL encryption support
- The website begins with https:// instead of http://
- An SSL certificate and private key are required
- Used when data between the server and the user needs to be protected
- Essential for production applications that require security

const https = require('https');
const fs = require('fs');

const options = {

  key: fs.readFileSync('private-key.pem'),
  
  cert: fs.readFileSync('certificate.pem')
};

const server = https.createServer(options, (req, res) => {

  res.end('we are using HTTPS')

});

server.listen(3000);

-----------------------------------------
HTTP/2 is faster and more efficient than HTTP/1.1 because:

1. It supports multiplexing (sending more than one request on the same connection)
2. It compresses headers to reduce data size
3. It reduces website load times
------------------------------------------
- Use the http module when:

1. Developing simple applications or for experimentation
2. Working in a local development environment
3. Creating internal APIs that don't require coding
4. Compatibility with legacy systems that only support HTTP/1.1

- Use the HTTP2 module when:
1. High performance is needed with heavy traffic
2. Modern applications that require HTTP/2 features
3. Improved user experience (faster loading)
4. Works with modern browsers that support HTTP/2

- Use the https module when:

1. Deploying the application to a production environment
2. Handling sensitive data (passwords, personal information)
3. Needing better SEO (search engines prefer HTTPS)
4. Security compliance requirements



