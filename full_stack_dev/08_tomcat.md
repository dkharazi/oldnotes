## Motivating Java Servlet
- A web application is essentially an application that allows a browser to connect to the application and talk to it via HTTP
- If you want to make a Java web application, then you don't want to write the HTTP server code every time
- This was automated via Java Application Servers
- Apache Tomcat is the most populat Java Application Server

## General Description of Java Servlet
- A java servlet is a Java software component that extends the capabilities of a web server
- Although servlets can respond to many types of requests, they most commonly implement web containers for hosting web applications on web servers
- Thus, they qualify as a server-side servlet web API
- Such web servlets are the Java counterpart to other dynamic content technologies, like PHP and ASP.NET

## Specifics about Java Servlets
- To deploy and run a servlet, a web container must be used
- A web container (also known as a servlet container) is essentially the component of a web server that interacts with the servlets
- The web container is responsible for managing the lifecycle of servlets, mapping a URL to a particular servlet and ensuring that the URL requester has the correct access rights
- The Servlet API, contained in the Java package hierarchy javax.servlet, defines the expected interactions of the web container and a servlet
- A Servlet is an object that receives a request and generates a response based on that request
- The basic Servlet package defines Java objects to represent servlet requests and responses, as well as objects to reflect the servlet's configuration parameters and execution environment
- The package javax.servlet.http defines HTTP-specific subclasses of the generic servlet elements, including session management objects that track multiple requests and responses between the web server and a client
- Servlets may be packaged in a WAR file as a web application

## General Description of Apache Tomcat
- Apache Tomcat is an open-source implementation of the Java Servlet
- Essentially, Apache Tomcat provides a pure Java HTTP web server environment, where Java code can run
- Tomcat 4.x was released with Catalina (a servlet container), Coyote (an HTTP connector) and Jasper (a JSP engine)

## References
- http://tomcat.apache.org/
- https://en.wikipedia.org/wiki/Apache_Tomcat
- https://en.wikipedia.org/wiki/Java_servlet
- https://www.reddit.com/r/AskProgramming/comments/b0rxvg/can_someone_eli5_what_a_java_servlet_is/
