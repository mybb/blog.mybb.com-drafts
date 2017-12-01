### Minimum Supported PHP Version for Upcoming MyBB Releases

When MyBB 1.8 was released in September 2014, it required a PHP version 5.2 or greater while the previous series, MyBB 1.6 (originally released 3rd August, 2010), required PHP 5.1 or greater. To put that into perspective, PHP 5.2 was released on 2nd November, 2006 and on 6th January, 2011 was declared end of life (End Of Life: meaning it will not receive any updates nor security fixes). So before MyBB 1.8 was even released, it was supporting PHP versions that had long since been marked end of life by the PHP Group.

Earlier this year we opened [a discussion](https://community.mybb.com/thread-195675.html) on what PHP version MyBB 2.0 would require. The intentions were that MyBB 2.0 would require PHP 7.0 and other environment requirements could be changed with each minor release (for example from 2.3 to 2.4).

With the recent discussion of introducing a MyBB 1.10 series and the uncertainty surrounding what this would mean for MyBB 2.0, we believe that we should start to see changes to PHP version requirements as early as MyBB 1.10.

PHP 5.2 has served us well but has not received any performance or security updates in over 6 years, supporting it actively hinders the development and modernisation of MyBB as a whole. Since then, there have been several other PHP releases made generally available and then reaching end of life status. The PHP Group maintain [a list of PHP versions which have reached end of life status](https://secure.php.net/eol.php).

In the interest of ensuring MyBB remains up to date with current best practices and to leverage the new features and optimisations generally found in new versions of PHP, we propose that the minimum PHP version requirement be increased from PHP 5.2 to either 5.6 (which has just over a year until it reaches EOL on 31st December, 2018) or 7.0 (which has around two years).

MyBB 1.10 development is underway (some PRs have entered the review stage and suggestions are being taken in the [1.10 Suggestions and Feedback](https://community.mybb.com/forum-199.html) forum). We are really keen to gather as much feedback as possible and to learn from our userbase what their concerns might be when met by a change as substantial as this.
