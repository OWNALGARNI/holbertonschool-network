What happens when you type https://www.google.com and press Enter?

When you enter https://www.google.com in your browser, a series of coordinated network and server-side processes are triggered to deliver the requested web page.

1) DNS Resolution

The browser needs to translate the domain name into an IP address.

- It first checks the browser and operating system cache.
- If the IP is not cached, it queries a DNS resolver.
- The resolver contacts root servers, then TLD servers (.com), and finally Google’s authoritative DNS servers.
- The result is one or more IP addresses for Google’s servers.


2) TCP/IP Connection

Once the IP address is known, the browser establishes a connection to port 443 (HTTPS).

- A TCP three-way handshake occurs: SYN → SYN-ACK → ACK.
- The IP protocol ensures packets are routed correctly across networks to Google’s infrastructure.


3) Firewall Filtering
The request passes through several security layers:
- Local firewall (device/router)
- ISP or network-level filtering.
-  Google’s edge firewalls
Only permitted HTTPS traffic continues toward the destination.

4) HTTPS / TLS Handshake

Before any data is exchanged, a secure connection is established:
- The server provides its SSL/TLS certificate.
- The browser verifies the certificate (issuer, validity, domain match).
- Both sides agree on encryption keys.
After this step, all communication is encrypted.

5) Load Balancing
The request reaches a load balancer:
- It distributes incoming traffic across multiple backend servers.
- Improves performance, scalability, and availability.
- May route requests based on location, health checks, or policies.


6) Web Server
A web server (e.g., Nginx) receives the request:
- Handles HTTP/HTTPS communication
- May terminate TLS or pass it internally
- Serves static content (HTML, CSS, images)
- For dynamic content, forwards the request to the application server

 
7) Application Server 
The application server processes the request logic:
- Handles authentication and sessions
- Executes business logic
- Generates dynamic responses (HTML or JSON)
- Interacts with other internal services if needed


8) Database Access
If necessary, the application queries a database:
- Retrieves or updates data (user info, search results, etc.)
- Executes optimized queries.
- Returns results to the application server.

9) Response to the Browser
Finally, the server sends back an encrypted HTTP response.
The browser then:
- Validates the response.
- Parses HTML.
- Requests additional resources (CSS, JS, images).
- Builds the DOM and CSSOM.
- Executes JavaScript.
- Renders the final page for the user.


Summary
In short:
DNS resolves the domain name, TCP/IP establishes the connection, TLS secures it, firewalls filter traffic, load balancers distribute requests, and the web/application/database layers generate and return the final page.