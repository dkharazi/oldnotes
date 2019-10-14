## General Description
- In a general sense, proxy implies someone or something acting on behalf of someone
- In a technical sense, proxy implies a server acting on behalf of another server
- There are two forms of web proxies: Forward Proxy and Reverse Proxy

## Forward Proxy
- A forward proxy is used by a client (i.e. client side)
- A forward proxy is the process of involving an intermediary server (on the client-side) to fulfill a request to a web server on the client's behalf
- Use-cases for a forward proxy:
	- A forward proxy can help clients get around firewalls and get access to restricted/blocked sites
- Example of a forward proxy:
	- A proxy server (i.e. proxy.example.com), set up on the client-side (e.g. John Smith),  receives an HTTP request for a web server (e.g. www.google.com, some blocked site, etc.)

## Reverse Proxy
- A reverse proxy is used by a server (i.e. server-side)
- A reverse proxy is the process of involving an intermediary server (on the server-side) that takes requests from the client and forwards those requests to the web server
- Tools for setting up reverse proxies include Nginx and HaProxy
- Use-cases for a reverse proxy:
	- A reverse proxy can act as an HTTP load balancer (i.e. Nginx) to distribute web traffic across several application servers, which will improve performance
	- A reverse proxy can act as an added layer of security for main web servers, since clients are only communicating with a proxy server directly, rather than the web servers
- Example of a reverse proxy:
	- A proxy server (i.e. proxy.example.com), set up on the server-side (e.g. Google), receives an HTTP request for their web server (e.g. www.google.com)

## References
- https://medium.com/@abhishekbhardwaj510/forward-proxy-and-reverse-proxy-128e05e9e43a
