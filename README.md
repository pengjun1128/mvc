Phalcon MVC examples
====================

These are examples of MVC file structures you can employ using Phalcon >= 2.0.x

## Simple
This is a very simple MVC structure, it contains one model, two controllers and a view.
This example does not implement namespaces. Services are defined in public/index.php
without using Di\\FactoryDefault:

```
simple
├── apps
│   ├── controllers
│   │   ├── IndexController.php
│   │   └── ProductsController.php
│   ├── models
│   │   └── Products.php
│   └── views
│       └── products
│           └── index.phtml
└── public
    └── index.php
```

## Simple-Volt
This is a very simple MVC structure, it contains one model, two controllers and a view.
This example does not implement namespaces. Services are defined in public/index.php
without using Di\\FactoryDefault. This example uses Volt as template engine:

```
simple-volt/
├── app
│   ├── config
│   │   ├── config.php
│   │   ├── loader.php
│   │   └── services.php
│   ├── controllers
│   │   ├── ControllerBase.php
│   │   └── IndexController.php
│   └── views
│       ├── index
│       │   ├── index.volt
│       │   └── test.volt
│       ├── index.volt
│       └── layouts
│           └── template.volt
├── index.html
└── public
    └── index.php
```

## Simple-Subcontrollers
This is a very simple MVC structure, it contains one model, three controllers and a view.
Routes are defined in app/config/routes.php. Some routes point to controllers in a
subdirectory of controllers/:

```
simple-subcontrollers/
├── app
│   ├── config
│   │   ├── config.php
│   │   ├── loader.php
│   │   ├── routes.php
│   │   └── services.php
│   ├── controllers
│   │   ├── ControllerBase.php
│   │   ├── UsersController.php
│   │   └── admin
│   │       ├── ControllerBase.php
│   │       └── UsersController.php
│   └── views
│       ├── admin
│       │   └── users
│       │       └── index.volt
│       ├── index
│       │   └── index.volt
│       ├── index.volt
│       └── users
│           └── index.volt
├── index.html
└── public
    └── index.php
```

## Simple-Without-Application
Simple MVC structure without employing Phalcon\\Mvc\\Application.
This application does not use namespaces. This is an example of
how you can override Phalcon\\Mvc\\Application by implementing a similar functionality.
It also defines services without using Di\\FactoryDefault in public/index.php:

```
simple-without-application/
├── apps
│   ├── controllers
│   │   ├── IndexController.php
│   │   └── ProductsController.php
│   ├── models
│   │   └── Products.php
│   └── views
│       └── products
│           └── index.phtml
└── public
    └── index.php
```

## Single
This a single-module MVC structure without namespaces. You can find the module's directories
under the apps/ directory. This example does not use namespaces. All services are
initialized in public/index.php. Also, in this file, you can also find an application
class that initializes services and autoloaders grouping these tasks by methods.

```
single
├── apps
│   ├── controllers
│   │   ├── IndexController.php
│   │   └── ProductsController.php
│   ├── models
│   │   └── Products.php
│   └── views
│       ├── index.phtml
│       └── products
│           ├── index.phtml
│           └── test.phtml
└── public
    └── index.php
```

## Single-Namespaces
This a single-module MVC structure using namespaces. You can find the module's directories
under the apps/ directory. This example does not use namespaces. All services are
initialized in public/index.php. Also, in this file, you can also find an application
class that initializes services and autoloaders grouping these tasks by methods.

```
single-namespaces/
├── apps
│   ├── controllers
│   │   ├── IndexController.php
│   │   └── ProductsController.php
│   ├── models
│   │   └── Products.php
│   └── views
│       └── products
│           └── index.phtml
└── public
    └── index.php
```

## Single-Factory-Default
This a single-module MVC structure as is generated by Phalcon-Devtools.
Instead of initialize every service individually, it uses Di\\FactoryDefault:

```
single-factory-default/
├── app
│   ├── config
│   │   └── config.php
│   ├── controllers
│   │   ├── ControllerBase.php
│   │   ├── IndexController.php
│   │   └── TestController.php
│   └── views
│       ├── index
│       │   └── index.phtml
│       └── index.phtml
├── index.html
└── public
    └── index.php
```

## Single-Camelized-Dirs
This a single-module MVC structure. All files and directories are camelized (including views):

```
single-camelized-dirs/
├── App
│   ├── Config
│   │   ├── Loader.php
│   │   └── Services.php
│   ├── Controllers
│   │   ├── IndexController.php
│   │   └── ProductsController.php
│   ├── Models
│   │   └── Products.php
│   └── Views
│       ├── Index
│       │   └── Index.phtml
│       └── Products
│           └── Index.phtml
└── public
    └── index.php
```

# Multiple
This a multi-module MVC structure. This example implements two modules: frontend and backend.
By default frontend is served if no route to backend is asked. You can define which routes
use one module or another in public/index.php:

```
multiple/
├── apps
│   ├── backend
│   │   ├── Module.php
│   │   ├── controllers
│   │   │   ├── IndexController.php
│   │   │   ├── LoginController.php
│   │   │   └── ProductsController.php
│   │   ├── models
│   │   │   └── Products.php
│   │   └── views
│   │       ├── login
│   │       │   └── index.phtml
│   │       └── products
│   │           └── index.phtml
│   ├── frontend
│   │   ├── Module.php
│   │   ├── controllers
│   │   │   ├── IndexController.php
│   │   │   ├── ProductsController.php
│   │   │   └── UsersController.php
│   │   ├── models
│   │   │   └── Products.php
│   │   └── views
│   │       └── products
│   │           └── index.phtml
└── public
    └── index.php
```

# Multiple-Volt
This a multi-module MVC structure. This example implements two modules: frontend and backend.
By default frontend is served if no route to backend is asked. You can define which routes
use one module or another in public/index.php. Volt is used as template engine:

```
multiple-volt/
├── apps
│   └── frontend
│       ├── Module.php
│       ├── config
│       │   └── config.php
│       ├── controllers
│       │   ├── ControllerBase.php
│       │   └── IndexController.php
│       └── views
│           ├── index
│           │   ├── index.volt
│           ├── index.volt
├── config
│   ├── modules.php
│   └── services.php
├── index.html
└── public
    └── index.php
```

# Multiple-Shared-Views
This a multi-module MVC structure with a common views directory:

```
multiple-shared-views/
├── apps
│   ├── common
│   │   └── views
│   │       ├── index
│   │       │   └── index.phtml
│   │       ├── index.phtml
│   │       └── products
│   │           └── index.phtml
│   └── modules
│       ├── backend
│       │   ├── Module.php
│       │   ├── controllers
│       │   │   ├── IndexController.php
│       │   │   └── ProductsController.php
│       │   └── models
│       │       └── Products.php
│       └── frontend
│           ├── Module.php
│           └── controllers
│               └── IndexController.php
└── public
    └── index.php
```

# Multiple-Factory-Default
This a multi-module MVC structure as is generated by Phalcon-Devtools:

```
multiple-factory-default/
├── apps
│   └── frontend
│       ├── Module.php
│       ├── config
│       │   └── config.php
│       ├── controllers
│       │   ├── ControllerBase.php
│       │   └── IndexController.php
│       └── views
│           ├── index
│           │   └── index.phtml
│           └── index.phtml
├── index.html
└── public
    └── index.ph
```


# Multiple-Service-Layer-Model
This a multi-module MVC structure with model service layer pattern implemented:

```
multiple-service-layer-model/
├── apps
│   ├── config
│   │   ├── config.php
│   │   ├── modules.php
│   │   └── services.php
│   ├── models
│   │   ├── entities
│   │   │   └── User.php
│   │   ├── repositories
│   │   │   ├── Exceptions
│   │   │   │   └── InvalidRepositoryException.php
│   │   │   ├── Repositories.php
│   │   │   └── Repository
│   │   │       └── User.php
│   │   └── services
│   │       ├── Exceptions
│   │       │   └── InvalidServiceException.php
│   │       ├── Service
│   │       │   └── User.php
│   │       └── Services.php
│   └── modules
│       └── frontend
│           ├── Module.php
│           ├── controllers
│           │   ├── ControllerBase.php
│           │   └── IndexController.php
│           └── views
│               ├── index
│               │   └── index.phtml
│               └── index.phtml
├── database.sql
├── index.html
├── public
│   └── index.php
└── tests
    ├── Services
    │   └── UserServiceTest.php
    ├── TestHelper.php
    ├── UnitTestCase.php
    └── phpunit.xm
```

# Micro
A micro-framework-like application:

```
micro
└── index.php
```

# Micro-Factory-Default
A micro-framework-like application as is generated by Phalcon-Devtools:

```
micro-factory-default/
├── config
│   └── config.php
├── index.html
├── public
│   └── index.php
└── views
    ├── 404.phtml
    └── index.phtml
```
