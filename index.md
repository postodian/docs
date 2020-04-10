# API Reference

The Postodian API is organized around [REST](http://en.wikipedia.org/wiki/Representational_State_Transfer). Our API has predictable resource-oriented URLs, accepts [form-encoded](https://en.wikipedia.org/wiki/POST_(HTTP)#Use_for_submitting_web_forms) request bodies, returns [JSON-encoded](http://www.json.org/) responses, and uses standard HTTP response codes, authentication, and verbs.

The JSON format ensures maximum compatibility with industry-standard web application frameworks and programming languages. Using the POST method, you can perform requests and retrieve data using the GET method.

## API Key

A unique API key is assigned to you during registration. It is your gateway to interact with Postodian’s API endpoints. Use your key to authenticate all your requests using one of the [two authentication methods](/docs/authentication).

The key can be reset anytime from within your dashboard. This can be useful in the event that your key has been compromised. Please mind that resetting a key can break your application if it is not updated there at the same time.
