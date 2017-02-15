Login as a user
===============

To login as a parent user you'll have to call:

.. code-block:: objective-c

  [[KWSParent sdk] login: @"test@email.com"
                    with: @"testtest"
                     and: ^(BOOL operationOK) {
                      if (operationOK) {
                        // logged in OK
                      } else {
                        // logged in NOK
                      }
                    }];

The callback will pass the following values on completion:

=========== ======= ======
Value  	    Type    Meaning
=========== ======= ======
operationOK Boolean Login operation was successful
=========== ======= ======

From here on you'll be able get or update parent details
