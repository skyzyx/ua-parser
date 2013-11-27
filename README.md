# UAParser

This is a fork of the PHP library for the [ua-parser](https://github.com/tobie/ua-parser) project.


## Usage

```php
require("vendor/autoload.php");

use UAParser\UAParser;

$ua = "Mozilla/5.0 (Macintosh; Intel Ma...";

$parser = new UAParser;
$result = $parser->parse($ua);

print $result->ua->family;                // Safari
print $result->ua->major;                 // 6
print $result->ua->minor;                 // 0
print $result->ua->patch;                 // 2
print $result->ua->toString;              // Safari 6.0.2
print $result->ua->toVersionString;       // 6.0.2

print $result->os->family;                // Mac OS X
print $result->os->major;                 // 10
print $result->os->minor;                 // 7
print $result->os->patch;                 // 5
print $result->os->patch_minor;           // [null]
print $result->os->toString;              // Mac OS X 10.7.5
print $result->os->toVersionString;       // 10.7.5

print $result->device->family;            // Other

print $result->toFullString;              // Safari 6.0.2/Mac OS X 10.7.5
print $result->uaOriginal;                // Mozilla/5.0 (Macintosh; Intel Ma...
```

## Using Your Own Custom regexes.json File

You can use your own `regexes.json` file if you've customized the official file. I *strongly* encourage you to push back
any changes you may have so others can benefit. That said, to use your own do the following:

```php
require("vendor/autoload.php");

use UAParser\UAParser;

$parser = new UAParser("path/to/custom/regexes.json");
```

## Credits

Thanks to the [original ua-parser team](http://code.google.com/p/ua-parser/people/list) for making the YAML file
available for others to build upon.

Also, many thanks to the following major contributors to the PHP library:

* Dave Olsen
* Bryan Shelton
* Michael Bond
* @rjd22
* Timo Tijhof
* Marcus Bointon
* Pravin Dahal
