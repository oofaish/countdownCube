countdownCube
=============

CountdownCube is a jQuery plugin that is in the form of a bunch of rotating 3D cubes. You can see an example in http://www.cigari.co.uk/countdown

It uses CSS transitions to create the 3D rotating cube effects.

## Basics

Make sure you have jQuery loaded - link the following files:
```html
<link rel="stylesheet" href="countdownCube.css"/>
<script type="text/javascript" src="countdowncube.js"></script>
```

Add a new empty div to your page:
```html
<div id="counter"></div>
```
And then kick off a new counter, with a target time (using the [ISO 8601 format](https://en.wikipedia.org/wiki/ISO_8601)), and if you like cubeSize (in pixels), background color, and font color:
```javascript
$('#counter').countdownCube( {
  target: '2018-03-01T10:00:00Z',
  cubeSize: 50,
  background: 'rgba( 255, 150, 150, 0.8 )',
  color: 'white',
} );
```

You can have more than one countdownCube per page.

I have only tested it on latest Chrome, Firefox and Safari.

Feel free to use it as it wish, but I would appreciate a plug to my website http://www.cigari.co.uk

## Timezone support

Timezone can be specified in the string in serveral formats:
* adding a letter `Z` at the end on the timestring `'2018-03-01T01:00:00Z'`
* adding an offset  with respect to UTC in the format `±hh:mm`: `'2018-03-01T01:00:00-05:00'` (this is the timezone of New York (US))

Support for timezones expressed as `'Continent/City'` can be added with the [`moment.js`](http://momentjs.com/) and  [`moment-timezone.js`](http://momentjs.com/timezone/) libraries.

For example, you can add them using the following CDNs:
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.20.1/moment.min.js" type="text/javascript"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment-timezone/0.5.14/moment-timezone-with-data-2012-2022.min.js" type="text/javascript"></script>
```

You can specify the timezone with the option `targetTimezone`:
```javascript
$('#counter').countdownCube( {
  target: '2018-03-01T10:00:00',
  targetTimezone: 'America/New_York',
  cubeSize: 50,
  background: 'rgba( 255, 150, 150, 0.8 )',
  color: 'white',
} );
```
see the [documentation of `moment-timezone.js`](http://momentjs.com/timezone/docs/#/using-timezones/).

The legacy syntax (using the built-in `Date` object) is still supported but may be incosistent across browsers. Timezone :
```javascript
$('#counter').countdownCube( {
  target: new Date('2018-03-01T10:00:00'),
  cubeSize: 50,
  background: 'rgba( 255, 150, 150, 0.8 )',
  color: 'white',
 } );
```

### Legacy `Date` objects

Note that if you use the legacy format and don't specify any timezone the browser will infer from the browser's local time:
```javascript
$('#counter').countdownCube( {
  /* target time in the local timezone of the browser */
  target: new Date('2018-03-01T10:00:00'),
  cubeSize: 50,
  background: 'rgba( 255, 150, 150, 0.8 )',
  color: 'white',
 } );
```

You can force UTC in the adding a `Z` at the end of the time string, as specified in the ISO 8601:
```
$('#counter').countdownCube( {
  /* target time in UTC */
  target: new Date( '2018-03-01T10:00:00Z' ),
  cubeSize: 50,
  background: 'rgba( 255, 150, 150, 0.8 )',
  color: 'white',
 } );
```

## Options

* `showDaysOnly`: if set to true shows the differences only up to days (default: `false`)

* `labelsTranslations`: you can specify a dictionary that can be used to translate the labels (year, month, day. hour, minute, second)

```javascript
$('#counter-days-only').countdownCube( {
  target: new Date( 'March 1, 2018 10:00:00' ),
  cubeSize: 150,
  background:  '#ffffff',
  color: 'blue',
  labelsTranslations: {'year': 'anni',
                       'month': 'mesi',
                       'day': 'giorni',
                       'hour': 'ore',
                       'minute': 'minuti',
                       'second': 'secondi'
                       },
  showDaysOnly: true,
} );
```

* `onEnd`: expects a function that is triggered when the counter reaches the end. The default does nothing. A typical use is hiding the counter and showing a different - previously invisible - element of the page. This gives the effect of something appearing when the countdown ends. Here's an example:
```
$('#counter').countdownCube( {
  target: '2018-12-03T11:00:00Z',
  onEnd: function(e) {
           $('#counter').hide();
           $('#after').show();
         },
  } );
```
* `triggerEnd`: the default is `false`, if set to `true` triggers the `onEnd` function even after the countdown has expired. Otherwise the counter shows the writing `LOADING...`.

Copyright (c) 2013 Ali Cigari @oofaish
