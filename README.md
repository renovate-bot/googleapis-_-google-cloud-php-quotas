# Google Cloud Quotas for PHP

> Idiomatic PHP client for [Google Cloud Quotas](https://cloud.google.com).

[![Latest Stable Version](https://poser.pugx.org/google/cloud-quotas/v/stable)](https://packagist.org/packages/google/cloud-quotas) [![Packagist](https://img.shields.io/packagist/dm/google/cloud-quotas.svg)](https://packagist.org/packages/google/cloud-quotas)

* [API documentation](https://cloud.google.com/php/docs/reference/cloud-quotas/latest)

**NOTE:** This repository is part of [Google Cloud PHP](https://github.com/googleapis/google-cloud-php). Any
support requests, bug reports, or development contributions should be directed to
that project.

### Installation

To begin, install the preferred dependency manager for PHP, [Composer](https://getcomposer.org/).

Now, install this component:

```sh
$ composer require google/cloud-quotas
```

> Browse the complete list of [Google Cloud APIs](https://cloud.google.com/php/docs/reference)
> for PHP

This component supports both REST over HTTP/1.1 and gRPC. In order to take advantage of the benefits
offered by gRPC (such as streaming methods) please see our
[gRPC installation guide](https://cloud.google.com/php/grpc).

### Authentication

Please see our [Authentication guide](https://github.com/googleapis/google-cloud-php/blob/main/AUTHENTICATION.md) for more information
on authenticating your client. Once authenticated, you'll be ready to start making requests.

### Sample

```php
Google\ApiCore\ApiException;
Google\Cloud\CloudQuotas\V1\Client\CloudQuotasClient;
Google\Cloud\CloudQuotas\V1\GetQuotaInfoRequest;
Google\Cloud\CloudQuotas\V1\QuotaInfo;

// Create a client.
$cloudQuotasClient = new CloudQuotasClient();

// Prepare the request message.
$request = (new GetQuotaInfoRequest())
    ->setName($formattedName);

// Call the API and handle any network failures.
try {
    /** @var QuotaInfo $response */
    $response = $cloudQuotasClient->getQuotaInfo($request);
    printf('Response data: %s' . PHP_EOL, $response->serializeToJsonString());
} catch (ApiException $ex) {
    printf('Call failed with message: %s' . PHP_EOL, $ex->getMessage());
}
```

See the [samples directory](https://github.com/googleapis/google-cloud-php-quotas/tree/main/samples) for a canonical list of samples.

### Debugging

Please see our [Debugging guide](https://github.com/googleapis/google-cloud-php/blob/main/DEBUG.md)
for more information about the debugging tools.

### Version

This component is considered GA (generally available). As such, it will not introduce backwards-incompatible changes in
any minor or patch releases. We will address issues and requests with the highest priority.

### Next Steps

1. Understand the [official documentation](https://cloud.google.com/docs/quota/api-overview).
