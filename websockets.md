# WebSockets

WebSockets allow a client and server to talk with each other.

HTTP requests close their connection after a server sends a response.
(INCLUDE DIAGRAM)

When I was in college, there was a website you would go on to get your grades. I would keep refreshing my browser, waiting for my grades to appear. This is an example of polling.
(INCLUDE DIAGRAM)

We want to know when something on the server has changed. With traditional HTTP requests, the server can only respond to someone's request. The server can't communicate on its own.

WebSockets sets up a persistent connection between a client and a server. This allow servers to send information without needing a request.
(INCLUDE DIAGRAM)


## Considerations
Should you use WebSockets for your project? It depends.
* How frequent are your events?
  * If they're very frequent, like a stock market application, you might want WebSockets
* How long is the connection?
 * If the connection if very long, like a chat application, you might want WebSockets
* How quickly does the UI need to display the information?
 * If we need quick feedback, like a stock market application, you might want WebSockets
* Should we cache the data?
 * If you need to cache the data, like a text-only webpage, you might *not* want WebSockets
