Endroid QR Code Bundle
======================

[![Build Status](https://secure.travis-ci.org/endroid/QrCodeBundle.png)](http://travis-ci.org/endroid/QrCodeBundle)

This bundle provides a default controller for generating QR codes using the Endroid QR Code (endroid/QrCode) library. No
configuration or extension loading is required. You only need to load the routing file.

[![knpbundles.com](http://knpbundles.com/endroid/QrCodeBundle/badge-short)](http://knpbundles.com/endroid/QrCodeBundle)

## Requirements

* Symfony
* Dependencies:
 * [`QrCode`](https://github.com/endroid/QrCode)

## Installation

### Add in your composer.json

``` js
{
    "require": {
        "endroid/qrcode-bundle": "dev-master"
    }
}
```

### Install the bundle

``` bash
$ curl -s http://getcomposer.org/installer | php
$ php composer.phar update endroid/qrcode-bundle
```

Composer will install the bundle to your project's `vendor/endroid` directory.

### Enable the bundle via the kernel

``` php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Endroid\Bundle\QrCodeBundle\QrCodeBundle(),
    );
}
```

## Routing

Add the following section to your routing to be able to reach the controller.

``` yml
EndroidQrCodeBundle:
    resource:   "@QrCodeBundle/Controller/"
    type:       annotation
    prefix:     /qrcode
```

## Twig extension

The bundle also provides a Twig extension for quickly generating QR code urls.

``` twig
<img src="{{ qrcode_url(message) }}" />
```

## Configuration

No configuration required.

## Usage

After installation and configuration, QR codes can be generated by appending the QR code text to the url as mounted,
followed by .png, .jpg or .gif. For the example given above, this would be /qrcode/Life_is_too_short_to_be_generating_qr_codes.png.