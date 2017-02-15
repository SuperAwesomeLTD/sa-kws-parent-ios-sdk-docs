Creating a new user
===================

You can create a new user by calling:

.. code-block:: objective-c

  [[KWSParent sdk] create: @"test@email.com"
                     with: @"testtest"
                      and: ^(KWS_CREATE_PARENT_STATUS status) {

                        if (status == CREATED) {
                          // user created OK
                        } else {
                          // there was an error creating user
                        }

                      }];

The callback will pass the following values on completion:

======= ======================== ======
Value   Type                     Meaning
======= ======================== ======
status  KWS_CREATE_PARENT_STATUS End status of the operation
======= ======================== ======

The **status** parameter may have the following values:

================== ======
Value              Meaning
================== ======
CREATED            User was authenticated successfully
DUPLICATE    	     The email is already in use
INVALID_EMAIL      Parent email is invalid
INVALID_PASSWORD   Password is less than 8 characters
NETWORK_ERROR      Other network error
================== ======

From here on you'll be able get or update parent details
