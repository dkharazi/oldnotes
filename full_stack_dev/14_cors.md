## Defining an Origin
- 

## Defining Same-Origin Policy
- The same-origin policy is a crtical security mechanism
- The same-origin policy controls interactions between two different origins

## Motivating CORS
- When we say "interactions between two different origins," we're referring to browser-hosted JavaScript code interacting with the server of the site
- Interactions between two different origins are placed into three categories:
	- Cross-origin *writes*
		- These are typically allowed
		- These refer to links, redirects, and form submissions
	- Cross-origin *reads*
		- These are typically disallowed
		- However, read access via embedding is typically allowed
		- 
	- Cross-origin *embedding*
		- Theser are typically allowed
		- These refer to the following
			- JavaScript with `<script src="..."></script>`
			- CSS applied with `<link rel="stylesheet" href="...">`
			- Images displayed by `<img>`
			- Media played by `<video>`
			- Anything embedded by `<iframe>`
- Some examples of interactions between two different origins are the following:
	- Calling `[XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)`
	- Requesting for an `[<img>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)` element
- Interactions between two different origins are placed into three categories:
	- Cross-origin *writes* are typically allowed
		- This includes links, redirects, form submission

## Defining CORS
- CORS is used to allow cross-origin access
- In other words, CORS is a part of HTTP that lets servers specify what hosts are permitted to load content from that server

## References
- https://auth0.com/blog/cors-tutorial-a-guide-to-cross-origin-resource-sharing/- https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy
- https://stackoverflow.com/questions/50933122/same-origin-policy-writes-allowed
