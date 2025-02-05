
# What is a REST API?

- REST: Representational State Transfer 
- API: Application Programming Interface

## API

An API is a publicly published way of interacting with a system.


## REST

A REST API is much like what goes on behind the scenes with a web browser.
For example, if you google the word "foo" and then look at the address bar of
your browser, you will see something like this.

https://www.google.com/search?client=safari&rls=en&q=foo&ie=UTF-8&oe=UTF-8

Google provides what is basically a REST API.   The idea of a REST API is
a *service provider* provides a set of services through what are called
*endpoints*.  Each endpoint has a set of *parameters* (or *arguments*) that can
be passed to it, and returns a well defined *response*.

In the example above...

- service provider:   https://www.google.com
- endpoint:   /search
- parameters: client=safari&rls=en&q=foo&ie=UTF-8&oe=UTF-8

The list of parameters/arguments can be further subdivided into individual
parameters.  In this case...

- client=safari
- rls=en
- q=foo
- ie=UTF
- oe=UTF-8

The parameters tell the service what is being requested and some other
information.


- client:  what type of web browser made the request
- rls:     the language being used for the request
- q:       the string to search for
- ie=UTF   technical information about the characters in the request
- oe=UTF-8 similar to above

When the endpoint receives the arguments, it returns a response that the web
browser displays for the user.

The interesting thing about a REST API is it allows the same thing as
accomplished by the browser but using a programmimmg language instead.  Python
code for the google request...

    url_base = 'https://www.google.com'
    endpoint = '/search'
    args = dict(client='safari', rls='en', q='foo')
    resp = httpx.get(url_base+endpoint, params=args)

Now we have the search results available in the Python language and therefore we
have the full power of that, instead of being confined to looking at a web page.


