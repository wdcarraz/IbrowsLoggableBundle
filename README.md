IbrowsLoggableBundle
=============================

Symfony2 Bundle that will track every Entity change on your Project and save it to a log table. Your Project get's some kind of confirmability with this Bundle.

It also provide some methods to get back an entity to a earlier version.

Install & setup the bundle
--------------------------

1. Add IbrowsLoggableBundle in your composer.json:

	```js
	{
	    "require": {
	        "ibrows/loggable-bundle": "~1.0",
	    }
	}
	```

2. Now tell composer to download the bundle by running the command:

    ``` bash
    $ php composer.phar update ibrows/loggable-bundle
    ```

    Composer will install the bundle to your project's `ibrows/loggable-bundle` directory. ( PSR-4 )

3. Add the bundles to your `AppKernel` class

    ``` php
    // app/AppKernerl.php
    public function registerBundles()
    {
        $bundles = array(
            // ...
            new Stof\DoctrineExtensionsBundle\StofDoctrineExtensionsBundle(),
            new Ibrows\LoggableBundle\IbrowsLoggableBundle(),
            // ...
        );
        // ...
    }
    ```

4. Recommend config of stof_doctrine_extensions

    ``` yml
    stof_doctrine_extensions:
        orm:
            default:
              softdeleteable: true
              loggable: true
        class:
            loggable: Ibrows\LoggableBundle\Listener\LoggableListener
    ```
