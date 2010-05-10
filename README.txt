// $Id$

Login one time README

CONTENTS OF THIS FILE
----------------------

  * Introduction
  * Installation
  * Configuration
  * Usage
  * API Usage

INTRODUCTION
------------
Maintainer: Daniel Braksator (http://drupal.org/user/134005)

Instructions on http://drupal.org/project/login_one_time.


INSTALLATION
------------
1. Copy login_one_time folder to modules directory.
2. At admin/build/modules enable the Login One Time module.
3. Enable permissions at admin/user/permissions.


CONFIGURATION
-------------
The configuration page for this module is at:
User management > Login one time (admin/user/login_one_time)

There is also an email template configurable at:
User management > User settings (admin/user/settings)


USAGE
-----
There are two inbuilt ways to send one time login links:

1) Pressing the "Send one-time login link [...]" button in a user profile.

2) Using the operations on the user administration page, or with the module
   'Views Bulk Operations'. http://drupal.org/project/views_bulk_operations


API USAGE
---------

To output a button, that when pressed sends an email to the email address of
the supplied user $account giving them a one-time login link to the page that 
the code was called from, use this PHP:

  print login_one_time_button($account);


If you would like them to start on a particular page, such as the front page,
you can add an extra parameter $path like so:

  print login_one_time_button($account, $path);


If you would like to skip the button and just call a function that sends the
email straight away ($path optional):

  login_one_time_send_mail($account, $path);


You can also easily do a mass send of links. In this case, $accounts is an
array of User IDs ($path optional):

  login_one_time_bulk_send_mail($accounts, $path);
