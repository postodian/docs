# API Reference

The Postodian API is organized around [REST](http://en.wikipedia.org/wiki/Representational_State_Transfer). Our API has predictable resource-oriented URLs, accepts [form-encoded](https://en.wikipedia.org/wiki/POST_(HTTP)#Use_for_submitting_web_forms) request bodies, returns [JSON-encoded](http://www.json.org/) responses, and uses standard HTTP response codes, authentication, and verbs.

Familiarize yourself with the core concepts of the JSON (JavaScript Object Notation) data format. JSON is a common, language-independent data format that provides a simple text representation of arbitrary data structures. For more information, see [json.org](http://json.org/). The JSON format ensures maximum compatibility with industry-standard web application frameworks and programming languages.

Using the GET method, you can retrieve data from the Postodian API.

## API Key

A unique API key is assigned to you during registration. You can find it in your publication’s settings. It is your gateway to interact with Postodian’s API endpoints. Use your key to [authenticate requests](https://postodian.com/docs/authentication).

The key can be reset anytime from within your dashboard. This can be useful in the event that your key has been compromised. Please mind that resetting a key can break your application if it is not updated there at the same time.
