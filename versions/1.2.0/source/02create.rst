Creating a new user
===================

You can create a new user by calling:

.. code-block:: objective-c

  [[KWSParent sdk] createUser: @"test@email.com"
                 withPassword: @"testtest"
                  andResponse: ^(KWSParentCreateUserStatus status) {

                        if (status == KWSParent_CreateUser_Success) {
                          // user created OK
                        } else {
                          // there was an error creating user
                        }

                      }];

The callback will pass the following values on completion:

======= ========================= ======
Value   Type                      Meaning
======= ========================= ======
status  KWSParentCreateUserStatus End status of the operation
======= ========================= ======

The **status** parameter may have the following values:

====================================== ======
Value                                  Meaning
====================================== ======
KWSParent_CreateUser_Success           User was authenticated successfully
KWSParent_CreateUser_DuplicateUsername The email is already in use
KWSParent_CreateUser_InvalidEmail      Parent email is invalid
KWSParent_CreateUser_InvalidPassword   Password is less than 8 characters
KWSParent_CreateUser_NetworkError      Other network error
====================================== ======

From here on you'll be able get or update parent details
