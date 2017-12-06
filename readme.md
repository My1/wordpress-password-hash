# PHP password_hash Reloaded
~~~
Originally by: ayeshrajans
Reloaded Version by My1
Tags: password, password hashing, password_hash, bcrypt, argon2, sodium, password security, security
Requires at least: 3.7
Tested up to: 4.9.1
Version: 0.1
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html
~~~
Makes Wordpress use PHP's native password_hash() functions for portable, stronger, and time-attack safe bcrypt hashes.

## Description

*Requires PHP 5.5 or later*


## Installation

1. Upload the plugin files to the `/wp-content/plugins/wp-pwhash-reloaded` directory, or install the plugin through the WordPress plugins screen directly.
1. Activate the plugin through the 'Plugins' screen in WordPress.
1. You are all set! There is nothing to configure. All existing users passwords will be rehashed on their next successful login. There is no configuration UI; it just works.


## Frequently Asked Questions

### Why PHP 5.5?

Call it mercy. The `password_*()` functions have been become available in PHP 5.5. there are shims but PHP5.5 is already End of Life long enough, and one should really use PHP 5.6 or later.

### Do I have to reset all existing passwords?

Not Needed. This plugin can detect old hashes, check and update them.
The only thing that could happen is you disabling this plugin AND going down to a PHP version older than 5.5. Even phpass is smart enough to check bcrypt hashes.

### What should I know about uninstalling?

see above, unless you downgrade PHP (which is a bad Idea) or wordpress changes phpass in a way that it wont try checking the passwords the way it does, no changes needed. otherwise passwords need a reset.

also if WP updates their Software to do native hashing this plugin can be safely axed no matter what.

### How do I confirm the new hashing algorithm is in use?

The easiest way would be to check your database from PHPMyAdmin or any other software in its line. Check if the password
hash field in your users table has the format `$2y$10...`. Those who have not updated their hashes will be have a different
format. However, if the plugin was unable to make its changes, you will see a notification in your Wordpress dashboard.
If you do not see anything, you are golden.

### PHP 7.2 has Argon2

Yes, and that's awesome. I will try to write something that allows you to set the password settings like you want, but first I need to learn how all of this stuff works.


## Changelog

### Reloaded 0.1
fixed breakage because PasswordHash class not yet existing in 4.8.2 (or possibly earlier, that was at least when I noticed it)

### original 1.0
* Initial release.
