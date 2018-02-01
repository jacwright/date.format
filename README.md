# date.format.js

This was developed to allow for the formatting of dates in JavaScript and ActionScript like [PHP](http://php.net/manual/en/function.date.php) can do. I actually just took the documentation from the [PHP date function](http://php.net/manual/en/function.date.php) and went down the list implementing every option that I could do easily.

Using it is simple, but you may need to refer to the available format string options often to remember how to use it. I always need to refer to [PHP’s date documentation](http://php.net/manual/en/function.date.php) every time I use it.

## Installation

**1. Download the script:**  
Option 1: [Download the repository without using git](https://github.com/jacwright/date.format/archive/master.zip)  
Option 2: `git clone https://github.com/jacwright/date.format.git`  

**2. Include the script:**  
`<script src="date.format.js"></script>`

## Usage
Escaping letters can be done by typing `\\` in front of a letter.

```javascript
var myDate = new Date();
alert(myDate.format('d-m-Y')); // Outputs "26-11-2017"
alert(myDate.format('d-m-Y H:i:s')); // Outputs "26-11-2017 15:24:30"
alert(myDate.format('M jS, Y')); // Outputs "Nov 26th, 2017"
alert(myDate.format('\\T\\o\\d\\a\\y \\i\\s d-m-Y')); // Outputs "Today is 26-11-2017"
```

## Supported identifiers

Taken from [PHP's `date` function](http://php.net/manual/en/function.date.php) and modified.
<table>
  <thead>
    <tr>
      <th>Format character</th>
      <th>Description</th>
      <th>Output</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th colspan="3">Day</th>
    </tr>
    <tr>
      <td><a href="#d" aria-hidden="true" class="anchor" id="d">d</a></td>
      <td>Day of the month, 2 digits with leading zeros</td>
      <td><code>01</code> to <code>31</code></td>
    </tr>
    <tr>
      <td><a href="#D" aria-hidden="true" class="anchor" id="D">D</a></td>
      <td>A textual representation of a day, three letters</td>
      <td><code>Mon</code> through <code>Sun</code></td>
    </tr>
    <tr>
      <td><a href="#j" aria-hidden="true" class="anchor" id="j">j</a></td>
      <td>Day of the month without leading zeros</td>
      <td><code>1</code> to <code>31</code></td>
    </tr>
    <tr>
      <td><a href="#l" aria-hidden="true" class="anchor" id="l">l (lowercase L)</a></td>
      <td>A full textual representation of the day of the week</td>
      <td><code>Sunday</code> through <code>Saturday</code></td>
    </tr>
    <tr>
      <td><a href="#N" aria-hidden="true" class="anchor" id="N">N</a></td>
      <td>ISO-8601 numeric representation of the day of the week</td>
      <td><code>1</code> (for Monday) through <code>7</code> (for Sunday)</td>
    </tr>
    <tr>
      <td><a href="#S" aria-hidden="true" class="anchor" id="S">S</a></td>
      <td>English ordinal suffix for the day of the month, 2 characters</td>
      <td><code>st</code>, <code>nd</code>, <code>rd</code> or <code>th</code>. Works well with <a href="#j">j</a></td>
    </tr>
    <tr>
      <td><a href="#w" aria-hidden="true" class="anchor" id="w">w</a></td>
      <td>Numeric representation of the day of the week</td>
      <td><code>0</code> (for Sunday) through <code>6</code> (for Saturday)</td>
    </tr>
    <tr>
      <td><a href="#z" aria-hidden="true" class="anchor" id="z">z</a></td>
      <td>The day of the year (starting from 0)</td>
      <td><code>0</code> through <code>365</code></td>
    </tr>
    <tr>
      <th colspan="3">Week</th>
    </tr>
    <tr>
      <td><a href="#W" aria-hidden="true" class="anchor" id="W">W</a></td>
      <td>ISO-8601 week number of year, weeks starting on Monday</td>
      <td>Example: <code>42</code> (the 42nd week in the year)</td>
    </tr>
    <tr>
      <th colspan="3">Month</th>
    </tr>
    <tr>
      <td><a href="#F" aria-hidden="true" class="anchor" id="F">F</a></td>
      <td>A full textual representation of a month, such as January or March</td>
      <td><code>January</code> through <code>December</code></td>
    </tr>
    <tr>
      <td><a href="#m" aria-hidden="true" class="anchor" id="m">m</a></td>
      <td>Numeric representation of a month, with leading zeros</td>
      <td><code>01</code> through <code>12</code></td>
    </tr>
    <tr>
      <td><a href="#M" aria-hidden="true" class="anchor" id="M">M</a></td>
      <td>A short textual representation of a month, three letters</td>
      <td><code>Jan</code> through <code>Dec</code></td>
    </tr>
    <tr>
      <td><a href="#n" aria-hidden="true" class="anchor" id="n">n</a></td>
      <td>Numeric representation of a month, without leading zeros</td>
      <td><code>1</code> through <code>12</code></td>
    </tr>
    <tr>
      <td><a href="#t" aria-hidden="true" class="anchor" id="t">t</a></td>
      <td>Number of days in the given month</td>
      <td><code>28</code> through <code>31</code></td>
    </tr>
    <tr>
      <th colspan="3">Year</th>
    </tr>
    <tr>
      <td><a href="#L" aria-hidden="true" class="anchor" id="L">L</a></td>
      <td>Whether it’s a leap year</td>
      <td><code>1</code> if it is a leap year, <code>0</code> otherwise.</td>
    </tr>
    <tr>
      <td><a href="#o" aria-hidden="true" class="anchor" id="o">o</a></td>
      <td>ISO-8601 year number. This has the same value as Y, except that if the ISO week number (W) belongs to the previous or next year, that year is used instead.</td>
      <td>Examples: <code>1999</code> or <code>2003</code></td>
    </tr>
    <tr>
      <td><a href="#Y" aria-hidden="true" class="anchor" id="Y">Y</a></td>
      <td>A full numeric representation of a year, 4 digits</td>
      <td>Examples: <code>1999</code> or <code>2003</code></td>
    </tr>
    <tr>
      <td><a href="#y" aria-hidden="true" class="anchor" id="y">y</a></td>
      <td>A two digit representation of a year</td>
      <td>Examples: <code>99</code> or <code>03</code></td>
    </tr>
    <tr>
      <th colspan="3">Time</th>
    </tr>
    <tr>
      <td><a href="#a" aria-hidden="true" class="anchor" id="a">a</a></td>
      <td>Lowercase Ante meridiem or Post meridiem</td>
      <td><code>am</code> or <code>pm</code></td>
    </tr>
    <tr>
      <td><a href="#A" aria-hidden="true" class="anchor" id="A">A</a></td>
      <td>Uppercase Ante meridiem or Post meridiem</td>
      <td><code>AM</code> or <code>PM</code></td>
    </tr>
    <tr>
      <td><a href="#B" aria-hidden="true" class="anchor" id="B">B</a></td>
      <td>Swatch Internet time</td>
      <td><code>000</code> through <code>999</code></td>
    </tr>
    <tr>
      <td><a href="#g" aria-hidden="true" class="anchor" id="g">g</a></td>
      <td>12-hour format of an hour without leading zeros</td>
      <td><code>1</code> through <code>12</code></td>
    </tr>
    <tr>
      <td><a href="#G" aria-hidden="true" class="anchor" id="G">G</a></td>
      <td>24-hour format of an hour without leading zeros</td>
      <td><code>0</code> through <code>23</code></td>
    </tr>
    <tr>
      <td><a href="#h" aria-hidden="true" class="anchor" id="h">h</a></td>
      <td>12-hour format of an hour with leading zeros</td>
      <td><code>01</code> through <code>12</code></td>
    </tr>
    <tr>
      <td><a href="#H" aria-hidden="true" class="anchor" id="H">H</a></td>
      <td>24-hour format of an hour with leading zeros</td>
      <td><code>00</code> through <code>23</code></td>
    </tr>
    <tr>
      <td><a href="#i" aria-hidden="true" class="anchor" id="i">i</a></td>
      <td>Minutes with leading zeros</td>
      <td><code>00</code> to <code>59</code></td>
    </tr>
    <tr>
      <td><a href="#s" aria-hidden="true" class="anchor" id="s">s</a></td>
      <td>Seconds, with leading zeros</td>
      <td><code>00</code> through <code>59</code></td>
    </tr>
    <tr>
      <td><a href="#v" aria-hidden="true" class="anchor" id="v">v</a></td>
      <td>Milliseconds</td>
      <td>Example: <code>654</code></td>
    </tr>
    <tr>
      <th colspan="3">Timezone</th>
    </tr>
    <tr>
      <td><a href="#e" aria-hidden="true" class="anchor" id="e">e</a></td>
      <td>Timezone identifier</td>
      <td><code>Atlantic/Azorest</code> or <code>Europe/Amsterdam</code></td>
    </tr>
    <tr>
      <td><a href="#I" aria-hidden="true" class="anchor" id="I">I (capital i)</a></td>
      <td>Whether or not the date is in daylights savings time</td>
      <td><code>1</code> if Daylight Savings Time, <code>0</code> otherwise.</td>
    </tr>
    <tr>
      <td><a href="#O" aria-hidden="true" class="anchor" id="O">O (capital o)</a></td>
      <td>Difference to Greenwich time (GMT) in hours</td>
      <td>Example: <code>+0200</code></td>
    </tr>
    <tr>
      <td><a href="#P" aria-hidden="true" class="anchor" id="P">P</a></td>
      <td>Difference to Greenwich time (GMT) with colon between hours and minutes</td>
      <td>Example: <code>+02:00</code></td>
    </tr>
    <tr>
      <td><a href="#T" aria-hidden="true" class="anchor" id="T">T</a></td>
      <td>Timezone setting of this machine</td>
      <td>Examples: <code>EST</code> or <code>MDT</code></td>
    </tr>
    <tr>
      <td><a href="#Z" aria-hidden="true" class="anchor" id="Z">Z</a></td>
      <td>Timezone offset in seconds. The offset for timezones west of UTC is always negative, and for those east of UTC is always positive.</td>
      <td><code>-43200</code> through <code>43200</code></td>
    </tr>
    <tr>
      <th colspan="3">Full Date/Time</th>
    </tr>
    <tr>
      <td><a href="#c" aria-hidden="true" class="anchor" id="c">c</a></td>
      <td><a href="https://www.iso.org/iso-8601-date-and-time-format.html" target="_blank">ISO 8601</a> formatted date</td>
      <td>Example: <code>2017-11-26T15:12:21+00:00</code></td>
    </tr>
    <tr>
      <td><a href="#r" aria-hidden="true" class="anchor" id="r">r</a></td>
      <td><a href="https://www.ietf.org/rfc/rfc2822.txt" target="_blank">RFC 2822</a> formatted date</td>
      <td>Example: <code>Thu, 21 Dec 2000 16:01:07 +0200</code></td>
    </tr>
    <tr>
      <td><a href="#U" aria-hidden="true" class="anchor" id="U">U</a></td>
      <td>Seconds since the Unix Epoch (January 1 1970 00:00:00 GMT)</td>
      <td>Example: <code>1501804996</code></td>
    </tr>
  </tbody>
</table>
