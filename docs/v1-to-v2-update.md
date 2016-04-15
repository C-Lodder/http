## Updating from v1 to v2

### PHP 5.3 support dropped

The HTTP package now requires PHP 5.4 or newer.

### PSR-7 Support

Version 2 of the HTTP package started to use PSR-7 compliant syntax. This means that custom transport drivers now need to formulate
their `Response` object using PSR-7 compliant syntax.

`
$response = new \Joomla\Http\Response;
$response->withBody($body);
$response->withHeader($headerName, $headerValue);
$response->withStatus($statusCode);
`

We encourage users of the package to use PSR-7 compliant code to retrieve information from the response object, however we are maintaining
support for retrieving the body, headers and status code through the same way as in version 1 of the HTTP package.

### Factory class methods no longer static

The methods of the `HttpFactory` class are no longer static.  Users must now instantiate the factory class to access its methods.

### cacert.pem no longer included

The HTTP package no longer includes a cacert.pem file. The file packaged with the `composer/ca-bundle` package is used instead per its logic.
