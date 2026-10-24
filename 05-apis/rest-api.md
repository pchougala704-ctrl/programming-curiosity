# REST APIs

REST (Representational State Transfer) is a set of architectural constraints for networked systems. A REST-style web API commonly represents things as resources, identifies them with URLs, and uses standard HTTP methods to act on them.

For example, an API might expose `/books` for a collection and `/books/42` for one book. `GET` can retrieve data, `POST` can create a resource, `PUT` or `PATCH` can update one, and `DELETE` can remove one. The exact meaning depends on the API's documented behavior.

People often call any JSON-over-HTTP service a REST API, but that does not necessarily mean it follows REST's full constraints. Clear resource names, consistent status codes, and useful documentation make an API easier to use even when it is not strictly RESTful.

## Challenge questions

- **57.** What are HTTP methods?
- **58.** Why do we have `GET`, `POST`, `PUT`, `PATCH`, and `DELETE`?

Read the [seven-lens answers](./challenge-answers.md#apis-seven-lens-answers).
