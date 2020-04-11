### Read: 07 - APIs continued
#### Rest
- Roy Fielding, he talks a lot about what those things point to in that research I was talking about. The whole world wide web is built on an architectural style called “REST”. REST provides a definition of a “resource”, which is what those things point to.
 A web page is a “representation” of a resource. Resources are just concepts. URLs--those things that you type into the browser... <br>
 Each of the systems would retrieve information from each other using a simple HTTP GET. If one system needs to add something to another system, it would use an HTTP POST. If a system wants to replace something in another system, it uses an HTTP PUT, or, to do a partial update, it'll hopefully use PATCH. The only thing left to figure out is what the data models should look like.

 #### SuperAgent 
 <!-- https://visionmedia.github.io/superagent/ -->
- Light-weight progressive ajax API crafted for flexibility, readability, and a low learning curve after being frustrated with many of the existing request APIs.
 - Request basics
A request can be initiated by invoking the appropriate method on the request object, then calling .then() (or .end() or await) to send the request. For example a simple GET request: <br>

HTTP method may also be passed as a string:

request('GET', '/search').then(success, failure);
Old-style callbacks are also supported, but not recommended. Instead of .then() you can call .end():

- The HTTP method defaults to GET, so if you wish, the following is valid:

 request('/search', (err, res) => {

 });
Setting header fields
Setting header fields is simple, invoke .set() with a field name and value:

 request
   .get('/search')
   .set('API-Key', 'foobar')
   .set('Accept', 'application/json')
   .then(callback);
	 - GET requests
The .query() method accepts objects, which when used with the GET method will form a query-string. The following will produce the path /search?query=Manny&range=1..5&order=desc.

 request

 - SuperAgent formats are extensible, however by default "json" and "form" are supported. To send the data as application/x-www-form-urlencoded simply invoke .type() with "form", where the default is "json". This request will POST the body "name=tj&pet=tobi".