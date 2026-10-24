# Request and response

Many web APIs use a request-response pattern. A client sends a request to a server, and the server sends back a response. The client might be a browser, a mobile app, or another service.

A request usually identifies an endpoint and includes a method, headers, and optionally a body. For example, a request might ask for a list of products or submit details for a new order. A response contains a status code, headers, and often data in a format such as JSON.

The response may indicate success, a client-side problem such as invalid input, or a server-side failure. Good API clients check status codes and handle network errors rather than assuming every request succeeds.

## Challenge questions

- **54.** What is a request?
- **55.** What is a response?
- **56.** Why do APIs commonly use JSON?
- **59.** What happens if an API takes 10 seconds to respond?
- **60.** What happens if the API server is completely down?
- **77.** What is CORS? (See the security answer linked below.)

Read the [seven-lens answers](./challenge-answers.md#apis-seven-lens-answers).

For the related browser security question, read the [seven-lens answer to question 77: What is CORS?](../07-security/challenge-answers.md#security-seven-lens-answers).
