# its-a-date

No need to know exact date format. Leave its-a-date to figure it out.

## Installation

```
$ npm install its-a-date
```
## Code Example

```js
var itsadate = require('its-a-date');

// Wed Aug 17 2011 15:44:00 GMT+0300 (Jerusalem Daylight Time)
itsadate.parse("5 years ago at 15:44");

// Wed Apr 11 1990 00:45:00 GMT+0300 (Jerusalem Daylight Time)
itsadate.parse("3 months after 11/01/1990");
```
## More Code Examples

### Parse Hour & Date

```js
// Fri Aug 19 2016 11:47:00 GMT+0300 (Jerusalem Daylight Time) 
itsadate.parse("11:47");

// Tue Mar 27 2012 14:05:00 GMT+0200 (Jerusalem Standard Time)
itsadate.parse("27.3.2012");

// Tue Mar 27 2012 12:00:00 GMT+0200 (Jerusalem Standard Time)
itsadate.parse("27/3/2012 12:00");
```

### Parse Relatives 

```js
// Thu Aug 18 2016 14:05:00 GMT+0300 (Jerusalem Daylight Time)
itsadate.parse("yesterday");

// Thu Aug 18 2016 16:20:00 GMT+0300 (Jerusalem Daylight Time)
itsadate.parse("yesterday at 16:20");

//Fri Aug 19 2011 14:05:00 GMT+0300 (Jerusalem Daylight Time)
itsadate.parse("5 years ago");

// Fri Aug 19 2011 15:44:00 GMT+0300 (Jerusalem Daylight Time)
itsadate.parse("5 years ago at 15:44");
```
### Parse the Extreme (Not Recommended) 

When its-a-date doesn't know what date it is, it will resolve current datetime. 
However many times it surprises.

```js
// Sun Jan 01 1984 14:05:00 GMT+0200 (Jerusalem Standard Time)
itsadate.parse('it was on the 1st of January, ' +
                    'the dark cold winter of 1984');

// Fri Aug 19 2016 14:05:15 GMT+0300 (Jerusalem Daylight Time)
itsadate.parse("pikachu");
```

### Learn More

Hit brag to console out example from each token implemented

```js
itsadate.brag()
```


### Exceptions

When date description has inner conflicts an exception will be thrown

```js
// ERROR: Two or more absolute modifications are not allowed on the same date entity
itsadate.parse('1st of november 02/03/2000')
```

## Motivation

1. Allows a user to type a date more naturally in a web page or social media.
2. Allows crawlers to parse relative dates easily.

## Strategy (How it works?)

A micro-compiler is implemented. It parses date part tokens &
interpret them as modifications on the perceived date.

## Upcoming Features
1. UTC control
2. Basic format hints, optional
3. Custom tokens insertion

## Git

https://github.com/bendorshai/its-a-date

## Note

The package is still at very early stages and it is not complete.

