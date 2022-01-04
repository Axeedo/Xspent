# Questions

## Question 1: About input validation

### How fastify processes unknown properties?

Unknown properties are skipped in fastify (at least with the given schemas).

### How fastify behaves if a known property is missing in the payload?

If a property is missing in the payload, fastify returns an error code, notifying that the property is required.

### What happens if an input property is null?

If an input property is null, and if it shouldn't follow a specific pattern, the null property is evaluated to zero if it's a number, to and empty string if it's a string.

## Question 2: About response serialisation

### How fastify processes unknown properties?

Unknown properties are skipped during serialisation.

### How fastify behaves if a known property is missing in the payload?

When fastify is faced with an unknown property during serialisation, it returns an internal server error (500).

## Question 3: Is input validation just a matter of types and schemae?

Input validation is about types and schemae so that we have better security and prevention of unforseen bugs (from just javascript).

We can also add code later for logical and syntaxic validation, which are a blind spots for types and schemae but are still potential vectors of attack.
