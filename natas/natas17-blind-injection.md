# Natas 17 — Blind Injection via Conditional Responses

## Context
The application processes user-controlled input on the server side
without directly returning the result of the executed operation.

The user does not see database output, but server responses differ
based on whether a condition is true or false.

## Vulnerability
User input is passed into a backend operation in an unsafe way,
allowing conditional logic to be evaluated based on sensitive data.

Although no direct output is returned, response behavior can be used
as an oracle to infer backend values.

## Exploitation Logic
By crafting conditional expressions and observing differences
in server responses, it is possible to determine whether a condition
is true or false.

Repeating this process allows character-by-character extraction
of sensitive information without direct data leakage.

## Impact
An attacker can extract sensitive data such as passwords
even when the application does not explicitly return query results.

This bypasses traditional output-based protections.

## Fix
Avoid passing user-controlled input into backend commands or queries.
Use safe APIs and parameterized operations, and ensure that
application responses do not leak conditional behavior.
