readable-timespan
=================

[![Build Status](http://img.shields.io/travis/aurbano/readable-timespan/master.svg?style=flat-square)](https://travis-ci.org/aurbano/readable-timespan)
[![Dependency Status](http://img.shields.io/david/aurbano/readable-timespan.svg?style=flat-square)](https://david-dm.org/aurbano/readable-timespan)
[![npm version](http://img.shields.io/npm/v/readable-timespan.svg?style=flat-square)](https://www.npmjs.org/package/readable-timespan)
[![license](http://img.shields.io/npm/l/readable-timespan.svg?style=flat-square)](https://www.npmjs.org/package/readable-timespan)

> npm package to get human readable timespans

Display timespans the way we understand them:

* 4 minutes
* 2 weeks
* 23 seconds
* 5m
* 8 months
* ...

##Install

```sh
$ npm install --save readable-timespans
```

##Usage

```js
var timespan = require('readable-timespans');

console.log("Last seen " + timespan.parse(5 * 60 * 1000) + " ago");
// Last seen 5 minutes ago
```

The `parse()` method takes one argument: the time difference in milliseconds, and returns the closest unit rounded up.

##Configuration

There are several settings that can be changed, this allows even localization in your language.

###timespan.set(options)

There are several options you can set:

* [second, minute, hour, week, month, year]: Different strings for unit names.
* [space]: Whether you want a space or not.
* [pluralize]: Whether it should return an 's' at the end when the number is > 1.

```js
var timespan = require('readable-timespans');

timespan.set({
    second: 's',
    minute: 'm',
    hour: 'h',
    day: 'd',
    week: 'w',
    month: 'mo',
    year: 'y',
    space: false,
    pluralize: false
});

// You will now get 5s instead of 5 seconds, 4m instead of 4 minutes and so on.
```

##Localization

You can set it to your language by overriding the names of the units.

For example in Spanish:
```js
var timespan = require('readable-timespans');

timespan.set({
    second: 'segundo',
    minute: 'minuto',
    hour: 'hora',
    day: 'dia',
    week: 'semana',
    month: 'mes',
    year: 'año'
});

// You will now get '5 segundos' instead of '5 seconds', '4 minutos' instead of '4 minutes' and so on.
```

------ 

## License

GPLv2 © [Alejandro U. Alvarez](http://urbanoalvarez.es)