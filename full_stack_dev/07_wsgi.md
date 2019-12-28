## General Description
- A web server gateway interface (or WSGI) is a server specification coded in Python
- In other words, a WSGI defines a standard interface for communication between an application (i.e. django or flask application) and an application/web server (i.e. nginx)
- The goal of a WSGI is to do the following:
	- Provide a simple yet comprehensive interface capable of supporting all interactions between a web server and an application
	- Support middleware components for pre- and post-processing of requests
- The pre- and post-processing of requests could include the following:
	- Logging
	- Formatting HTTP responses
	- Adding headers to HTTP responses
- The WSGI achieves this by simplifying and standardizing communication between the application and web server
- In turn, this ensures the communication between the two components is interchangeable and consistent

## Example of WSGI Function
```
def simple_app(environ, start_response):
	status = '200 OK'
	response_headers = [('Content-type','text/plain')]
	start_response(status, response_headers)
	return ['Hello world!\n']
```

## Benefits of WSGI from Example
- We're able to provide an HTTP header
	- From the statement status = '200 OK'
- We're able to format an HTTP header and body
	- From the statement response_headers = [('Content-type','text/plain')]
- We're able to being the HTTP response by calling the start_response function passed to every WSGI function
	- From the statement start_response(status, response_headers)
- We're able to return the HTTP body by returing an iterable in our WSGI function
	- From the statement return ['Hello world!\n']

## References
- http://ivory.idyll.org/articles/wsgi-intro/what-is-wsgi.html
- https://www.digitalocean.com/community/tutorials/how-to-set-up-django-with-postgres-nginx-and-gunicorn-on-ubuntu-14-04
- https://www.python.org/dev/peps/pep-0333/
- https://rufuspollock.com/2006/09/28/wsgi-middleware/
