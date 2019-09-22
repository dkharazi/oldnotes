## Stateful and Stateless Applications
- Statelessness is a property of a server running a service (code)
- In a Stateless Protocol/Application: 
	- No information about a transaction is maintained after a transaction is processed (i.e. some script processes the transaction)
	- There is no record of the state saved server-side
- In a Stateful Protocol/Application:
	- State information is kept even after a transaction has been processed (i.e. some script processes the transaction and sends data to the database to be saved)
	- Servers using Stateful Protocols maintain the status of the connection, processes, etc.
- Essentially, an application is stateful if any data (i.e. transformations, session data, etc.) is written to a database server at any time the application is running

## Examples of Stateless Applications
- An application reporting sales to business users (without saving any session data)
- A static application passing clients on to an individual microservice (without saving any session data)
- An application that is a tic-tac-toe game (without saving any session data)

## Examples of Stateful Applications
- An application reporting sales to business users, and monitoring and saving session users to a database
- An application for Spotify that tracks number of listens for each song

## Resources
- https://www.quora.com/What-is-the-difference-between-stateful-and-stateless-protocol
- https://softwareengineering.stackexchange.com/questions/346867/how-to-keep-applications-stateless
- https://www.bizety.com/2018/08/21/stateful-vs-stateless-architecture-overview/
