Installation
============

All the sources are hosted at `Github http://github.com/WhereGroup/DesktopIntegrationBundle`.

Update your composer.json
-------------------------

In order to use this bundle, add the following to your composer.json to make
the bundle known to composer:

    "repositories": {
        "wheregroup": {
            "type": "git",
            "url": "https://github.com/WhereGroup/DesktopIntegrationBundle.git"
        }
    }

Then add the following to the requirements in your composer.json

    "wheregroup/desktopintegration-bundle": "1.0.x-dev"

Finally, issue an ./composer.phar update to install the bundle. CAUTION: This
will also update all other packages within the constraints laid out in your
composer.json file - for example Doctrine will be upgraded as anything in the
2.2.3 to 2.3.x range is allowed.

Activate the bundle
-------------------

Active the bundle inside your app/AppKernel.php's registerBundles method by adding

new WhereGroup\DesktopIntegrationBundle\WhereGroupDesktopIntegrationBundle()

to the array of registered bundles.

Activate the URL routing
------------------------
Add the following lines to the app/config/routing.yml:

wheregroup_desktop_integration:
    resource: "@WhereGroupDesktopIntegrationBundle/Controller"
    prefix: "/di"
    type: annotation
