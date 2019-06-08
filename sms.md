# SMS Abstraction for PHP

Currently there's a lot of SMS providers out there, offering varying features, pricing, availability & reliability.
It would be useful to have an abstraction that would allow you to swap in providers without changing any of your implementation code

## Features to support
It's important that the abstraction supports most or all features of all providers in a generic way.

### Send Abstraction
- Support worldwide numbers
- Support alpha numeric senders & shortcodes
- Support different message encoding
- Support different message length limits (multipart)
- Support both single and bulk sms sending
- Provide a consistent return format for wrapping the provider's response, plus allowing access to the raw response
- Should throw generic exceptions

The implementing drivers/providers would then handle the specific logic for that provider under the hood.

### Errors
TODO: research errors across different SMS platforms & create list of standard exceptions

### Responses

TODO: research different SMS platforms response formats, and what information they provide after sending an sms (eg, message id, delivery status, etc)


## Handling Incoming SMS
Would also provide a an abstraction for handling incoming SMSes. Take a PSR-7 request and parse it in the driver, returning an entity that implements the sms interface


## Todos/Unknowns
- Should incoming and outgoing messages share a single interface, or should they be different?

I don't expect anyone to find this repo (yet), but if you would like to help out feel free to reach out to me :)
