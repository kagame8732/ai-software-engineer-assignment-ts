### What was the bug?

The `HttpClient` failed to refresh the authentication token when `oauth2Token` was provided as a plain JavaScript object instead of an instance of the `OAuth2Token` class.

### Why did it happen?

The original logic checked `!this.oauth2Token`. Since a plain object `{}` is truthy, the code skipped the refresh logic. However, the code only assigns the `Authorization` header if the token is an `instanceof OAuth2Token`, resulting in a missing header for plain objects.

### Why does your fix actually solve it?

The fix changes the condition to check if the token is a proper instance of `OAuth2Token`. If it's a plain object, `instanceof` returns `false`, triggering the `refreshOAuth2()` method and ensuring a valid instance is created before the header is set.

### What’s one realistic case / edge case your tests still don’t cover?

The tests do not cover a scenario where `refreshOAuth2()` might fail (e.g., a network error during refresh) or how the client should behave if the "fresh token" received from the server is also immediately expired.
