# date.format

This was developed to allow for the formatting of dates in JavaScript and ActionScript like PHP can do. I actually just took the documentation from the PHP date function and went down the list implementing every option that I could do easily. I know more support could be added, but I didn’t need it (and still don’t). If anyone embellishes on this let me know and we can post better versions!

Using it is simple, but you may need to refer to the available format string options often to remember how to use it. I always need to refer to PHP’s date documentation every time I use it. You may also escape letters to make them literal, but be sure to escape your escape so Javascript can handle the string correctly.

## Installation

- [Download the latest release (zipped).](https://github.com/jacwright/date.format/archive/master.zip)
- Clone the repo: `git clone https://github.com/jacwright/date.format`
- Install with [npm](https://www.npmjs.com): `npm install date.format.js`
- Install with [yarn](https://yarnpkg.com): `yarn add date.format.js`

## Usage
Escaping letters can be done by typing `\\` in front of the letter.

```javascript
var myDate = new Date();
alert(myDate.format('d-m-Y')); // Outputs "26-11-2017"
alert(myDate.format('M jS, Y')); // Outputs "Nov 26th, 2017"
alert(myDate.format('\\T\\o\\d\\a\\y \\i\\s d-m-Y')); // Outputs "Today is 26-11-2017"
```

## Localization

Include your preferred `locale.js` from the [locales folder](https://github.com/jacwright/date.format/tree/master/locales) and require it before you require `date.format`.
```html
<script src="locale.js"></script>
<script src="date.format.min.js"></script>
```

Localization is supported for the following [identifiers](https://github.com/jacwright/date.format#supported-identifiers):
- D
- l (lowercase L)
- F
- M

## Supported identifiers

Taken from [PHP's `date();` function](http://php.net/manual/en/function.date.php) and modified.

<table>
  <thead>
    <tr>
      <th>Format character</th>
      <th>Description</th>
      <th>Example</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th colspan="3">Day</th>
    </tr>
    <tr id="d">
      <td>d</td>
      <td>Day of the month, 2 digits with leading zeros</td>
      <td>01 to 31</td>
    </tr>
    <tr id="D">
      <td>D</td>
      <td>A textual representation of a day, three letters</td>
      <td>Mon through Sun</td>
    </tr>
    <tr id="j">
      <td>j</td>
      <td>Day of the month without leading zeros</td>
      <td>1 to 31</td>
    </tr>
    <tr id="l">
      <td>l (lowercase L)</td>
      <td>A full textual representation of the day of the week</td>
      <td>Sunday through Saturday</td>
    </tr>
    <tr id="N">
      <td>N</td>
      <td>ISO-8601 numeric representation of the day of the week</td>
      <td>1 (for Monday) through 7 (for Sunday)</td>
    </tr>
    <tr id="S">
      <td>S</td>
      <td>English ordinal suffix for the day of the month, 2 characters</td>
      <td>st, nd, rd or th. Works well with j</td>
    </tr>
    <tr id="w">
      <td>w</td>
      <td>Numeric representation of the day of the week</td>
      <td>0 (for Sunday) through 6 (for Saturday)</td>
    </tr>
    <tr id="z">
      <td>z</td>
      <td>The day of the year (starting from 0)</td>
      <td>0 through 365</td>
    </tr>
    <tr>
      <th colspan="3">Week</th>
    </tr>
    <tr id="W">
      <td>W</td>
      <td>ISO-8601 week number of year, weeks starting on Monday</td>
      <td>Example: 42 (the 42nd week in the year)</td>
    </tr>
    <tr>
      <th colspan="3">Month</th>
    </tr>
    <tr id="F">
      <td>F</td>
      <td>A full textual representation of a month, such as January or March</td>
      <td>January through December</td>
    </tr>
    <tr id="m">
      <td>m</td>
      <td>Numeric representation of a month, with leading zeros</td>
      <td>01 through 12</td>
    </tr>
    <tr id="M">
      <td>M</td>
      <td>A short textual representation of a month, three letters</td>
      <td>Jan through Dec</td>
    </tr>
    <tr id="n">
      <td>n</td>
      <td>Numeric representation of a month, without leading zeros</td>
      <td>1 through 12</td>
    </tr>
    <tr id="t">
      <td>t</td>
      <td>Number of days in the given month</td>
      <td>28 through 31</td>
    </tr>
    <tr>
      <th colspan="3">Year</th>
    </tr>
    <tr id="L">
      <td>L</td>
      <td>Whether it’s a leap year</td>
      <td>1 if it is a leap year, 0 otherwise.</td>
    </tr>
    <tr id="o">
      <td>o</td>
      <td>ISO-8601 year number. This has the same value as Y, except that if the ISO week number (W) belongs to the previous or next year, that year is used instead.</td>
      <td>Examples: 1999 or 2003</td>
    </tr>
    <tr id="Y">
      <td>Y</td>
      <td>A full numeric representation of a year, 4 digits</td>
      <td>Examples: 1999 or 2003</td>
    </tr>
    <tr id="y">
      <td>y</td>
      <td>A two digit representation of a year</td>
      <td>Examples: 99 or 03</td>
    </tr>
    <tr>
      <th colspan="3">Time</th>
    </tr>
    <tr id="a">
      <td>a</td>
      <td>Lowercase Ante meridiem and Post meridiem</td>
      <td>am or pm</td>
    </tr>
    <tr id="A">
      <td>A</td>
      <td>Uppercase Ante meridiem and Post meridiem</td>
      <td>AM or PM</td>
    </tr>
    <tr id="B">
      <td>B</td>
      <td>Swatch Internet time</td>
      <td>000 through 999</td>
    </tr>
    <tr id="g">
      <td>g</td>
      <td>12-hour format of an hour without leading zeros</td>
      <td>1 through 12</td>
    </tr>
    <tr id="G">
      <td>G</td>
      <td>24-hour format of an hour without leading zeros</td>
      <td>0 through 23</td>
    </tr>
    <tr id="h">
      <td>h</td>
      <td>12-hour format of an hour with leading zeros</td>
      <td>01 through 12</td>
    </tr>
    <tr id="H">
      <td>H</td>
      <td>24-hour format of an hour with leading zeros</td>
      <td>00 through 23</td>
    </tr>
    <tr id="i">
      <td>i</td>
      <td>Minutes with leading zeros</td>
      <td>00 to 59</td>
    </tr>
    <tr id="s">
      <td>s</td>
      <td>Seconds, with leading zeros</td>
      <td>00 through 59</td>
    </tr>
	<tr id="v">
      <td>v</td>
	  <td>Milliseconds</td>
	  <td>Example: 654</td>
	</tr>
    <tr>
      <th colspan="3">Timezone</th>
    </tr>
    <tr id="e">
      <td>e</td>
      <td>Timezone identifier</td>
      <td>Atlantic/Azorest, Europe/London</td>
    </tr>
    <tr id="I">
      <td>I (capital i)</td>
      <td>Whether or not the date is in daylights savings time</td>
      <td>1 if Daylight Savings Time, 0 otherwise.</td>
    </tr>
    <tr id="O">
      <td>O</td>
      <td>Difference to Greenwich time (GMT) in hours</td>
      <td>Example: +0200</td>
    </tr>
    <tr id="P">
      <td>P</td>
      <td>Difference to Greenwich time (GMT) with colon between hours and minutes</td>
      <td>Example: +02:00</td>
    </tr>
    <tr id="T">
      <td>T</td>
      <td>Timezone setting of this machine</td>
      <td>Examples: EST, MDT</td>
    </tr>
    <tr id="Z">
      <td>Z</td>
      <td>Timezone offset in seconds. The offset for timezones west of UTC is always negative, and for those east of UTC is always positive.</td>
      <td>-43200 through 43200</td>
    </tr>
    <tr>
      <th colspan="3">Full Date/Time</th>
    </tr>
    <tr id="c">
      <td>c</td>
      <td><a href="https://www.iso.org/iso-8601-date-and-time-format.html" target="_blank">ISO 8601</a> formatted date</td>
      <td>2004-02-12T15:19:21+00:00</td>
    </tr>
    <tr id="r">
      <td>r</td>
      <td><a href="https://www.ietf.org/rfc/rfc2822.txt" target="_blank">RFC 2822</a> formatted date</td>
      <td>Example: Thu, 21 Dec 2000 16:01:07 +0200</td>
    </tr>
    <tr id="U">
      <td>U</td>
      <td>Seconds since the Unix Epoch (January 1 1970 00:00:00 GMT)</td>
      <td>Example: 1501804996</td>
    </tr>
  </tbody>
</table>

## Contributing

Date.format is an open-source library and we would love for you to contribute! Head over to [CONTRIBUTING.md](https://github.com/jacwright/date.format/blob/master/CONTRIBUTING.md).
