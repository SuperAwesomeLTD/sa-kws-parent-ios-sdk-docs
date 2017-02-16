Overview
========

The Kids Web Services Parent SDK is designed to be as simple as possible while also enabling you to perform as many actions as possible.
It's built on top of the Kids Web Services API and tries to manage the complexity of interacting with it, as well as provide additional device specific features.

.. note::

	When using the SDK you will have to first authenticate as a user with the KWS back-end to be able to access the complete SDK functionality.

The Kids Web Services Parents SDK will then handle the following topics on your behalf:

+------------------------------------------------------+
| Create a new parent user                             |
+------------------------------------------------------+
| Login or logout as a user                            |
+------------------------------------------------------+
| Obtain parent data                                   |
+------------------------------------------------------+
| Update parent data                                   |
+------------------------------------------------------+

The SDK is built around a common singleton class called **KWSParent**. The singleton accessor method is simply called **sdk**.

Thus any method call will have the following pattern:

.. code-block:: objective-c

  [[KWSParent sdk] method];

Since most operations performed by the SDK involve doing network requests on KWS API, most method calls won't have a return type but will instead require a callback,
defined as an Objective-C block with a variable number of parameters.

.. code-block:: objective-c

  [[KWSParent sdk] method: ^(BOOL result) {
    // perform operation on result
  }];

Some methods also can have one or two parameters. In this case they will have the following signature:

.. code-block:: objective-c

  [[KWSParent sdk] method: (NSInteger) param1
                     with: (NSString*) param2
                      and: ^(BOOL result) {
    // perform operation on result
  }];

.. note::

  All method calls in the Kids Web Services Parent SDK have the callback method listed as last, making them ideal for Swift and it's functional notation.
