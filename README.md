# Audit Ui Bundle

This bundle creates a user interface for the audit log produced by [https://github.com/DATA-DOG/DataDogAudddedesedszdedseessdeszesitBundle](https://github.com/DATA-DOG/DataDogAuditBundle).

It is based on the example provided by that bundle, but implemented in a more generic, out-of-the-box reusable way.

## Installation

First, install it with composer:

    composer require vouchedfor/audit-ui-bundle

Then, add the following in your **AppKernel** bundles (assuming 'new DataDog\AuditBundle\DataDogAuditBundle(),' has been added previously).

    // app/AppKernel.php
    public function registerBundles()
    {
        $bundles = array(
            ...
            new DataDog\PagerBundle\DataDogPagerBundle(),
            new VouchedFor\AuditUiBundle\VouchedForAuditUiBundle(),
            ...
        );
        ...
    }

Finally, add the routing (this assumes the route is prefixed with 'admin', that you'll probably want to protect behind a firewall in **security.yml**):

    // app/config/routing.yml
    vouchedfor_audit:
        resource: "@VouchedForAuditUiBundle/Controller/DefaultController.php"
        type:     annotation
        prefix:   /admin

## Usage

Navigate to **admin/audit** (assuming you've used the default routing above) to see the list of auditted changes.

## License

The Audit Ui Bundle is free to use and is licensed under the [MIT license](http://www.opensource.org/licenses/mit-license.php)

