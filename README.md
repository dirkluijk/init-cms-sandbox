Networking init CMS sandbox based on the networking init CMS and the Symfony Standard Edition,
========================

Welcome to the init CMS Sandbox. This will get you started with a working CMS based
on the networking init CMS bundle and Symfony. The project is being developped by the
small hard working team at [net working AG][1] in Zürich.

This project is very much in an Alpha stage.

The installation of the sandbox is pretty much the same as a normal installation of Symfony project.

This document contains information on how to download, install, and start
using Symfony. For a more detailed explanation, see the [Installation][1]
chapter of the Symfony Documentation.

1) Installing the networking init CMS sandbox
---------------------------------------------

For the moment you will need to download an archive, then run composer to install the
dependencies. We will soon have the project on packagist, after that you will be able to use
the create-project command.

### Download an Archive File

First [download][2] and unpack the archive of the sandbox in your preferred location

	https://github.com/networking/init-cms-sandbox/archive/master.zip

Then change into the project directory

	cd path/to/install

### Use Composer (*recommended*)

As Symfony uses [Composer][3] to manage its dependencies, which is why we also use it.

If you don't have Composer yet, download it following the instructions on
http://getcomposer.org/ or just run the following command:

    curl -s http://getcomposer.org/installer | php

Composer will install the networking init CMS and all its dependencies under the
`path/to/install` directory.

Now you will need to install the dependencies, the following command will fill the vendors
folder with all the working guts in accordance with the versions defined in the composer.lock
file:

    php composer.phar install

Create a parameters.yml file:

	cp app/config/parameters.yml.dist app/config/parameters.yml

Now we just need to create some folders for our media in the web root directory and make it RW+

	cd web
	mkdir uploads uploads/media uploads/images
	chmod -R 777 uploads


2) Checking your System Configuration
-------------------------------------

Before starting coding, make sure that your local system is properly
configured for Symfony.

Execute the `check.php` script from the command line:

    php app/check.php

Access the `config.php` script from a browser:

    http://localhost/path/to/symfony/app/web/config.php

If you get any warnings or recommendations, fix them before moving on.

If all is good, you can move on to configuring the DB set up by clicking the
"Configure your Symfony Application online" link, or by editing the paramters.yml
file directly


3) Run the networking init CMS installation
-------------------------------------------

Now that the symfony application is more or less setup, it is time to load the CMS DBs and
fixtures, as well as create an admin user. The following command will do that for you. You will
be prompted to enter a username, email address and password, these will get you into the backend.


	php app/console networking:cms:install

Now you should be up and running.

What's inside?
---------------

The networking init CMS is based on a Symfony Standard Edition base plus a bit more

  * The sonata-admin bundle is the basis for the admin area

  * The routing of dynamic content is based on the Symfony CMF dynamic routing component

  * The Mopa bootstrap bundle for some twitter bootstrap goodness in the front end.

  * Twig is the only configured template engine;

  * Doctrine ORM/DBAL is configured;

  * Swiftmailer is configured;

  * Annotations for everything are enabled.

It comes pre-configured with the following bundles:

  * [**SonataAdminBundle**][4] The missing Symfony2 Admin Generator

  * [**SymfonyCmfRoutingExtraBundle**][5]  Symfony CMF Routing Extra Bundle
        capabilities

  * [**MopaBootstrapBundle**][6] MopaBootstrapBundle is a collection of code to
    integrate twitter's bootstrap into your symfony2 project


  * **FrameworkBundle** - The core Symfony framework bundle

  * [**SensioFrameworkExtraBundle**][7] - Adds several enhancements, including
    template and routing annotation capability

  * [**DoctrineBundle**][8] - Adds support for the Doctrine ORM

  * [**TwigBundle**][9] - Adds support for the Twig templating engine

  * [**SecurityBundle**][10] - Adds security by integrating Symfony's security
    component

  * [**SwiftmailerBundle**][11] - Adds support for Swiftmailer, a library for
    sending emails

  * [**MonologBundle**][12] - Adds support for Monolog, a logging library

  * [**AsseticBundle**][13] - Adds support for Assetic, an asset processing
    library

  * [**JMSSecurityExtraBundle**][14] - Allows security to be added via
    annotations

  * [**JMSDiExtraBundle**][15] - Adds more powerful dependency injection
    features

  * **WebProfilerBundle** (in dev/test env) - Adds profiling functionality and
    the web debug toolbar

  * **SensioDistributionBundle** (in dev/test env) - Adds functionality for
    configuring and working with Symfony distributions

  * [**SensioGeneratorBundle**][16] (in dev/test env) - Adds code generation
    capabilities


[1]:  http://web.networking.ch
[2]:  https://github.com/networking/init-cms-sandbox/archive/master.zip
[3]:  http://getcomposer.org/
[4]:  http://sonata-project.org/bundles/admin
[5]:  http://symfony.com/doc/master/cmf/bundles/routing-extra.html
[6]:  http://symfony.com/doc/master/cmf/bundles/routing-extra.html
[7]:  http://symfony.com/doc/2.1/bundles/SensioFrameworkExtraBundle/index.html
[8]:  http://symfony.com/doc/2.1/book/doctrine.html
[9]:  http://symfony.com/doc/2.1/book/templating.html
[10]:  http://symfony.com/doc/2.1/book/security.html
[11]: http://symfony.com/doc/2.1/cookbook/email.html
[12]: http://symfony.com/doc/2.1/cookbook/logging/monolog.html
[13]: http://symfony.com/doc/2.1/cookbook/assetic/asset_management.html
[14]: http://jmsyst.com/bundles/JMSSecurityExtraBundle/1.1
[15]: http://jmsyst.com/bundles/JMSDiExtraBundle/1.0
[16]: http://symfony.com/doc/2.1/bundles/SensioGeneratorBundle/index.html
