# Console++ - enhance your `console`

**Console++** makes your `console` awesomeR.

## How does it make it awesomeR?

Like this:

```javascript
// here console is not that awesomeR

require("console++");
// or
require("./console++.js"); //< if downloaded locally

// now console is very awesomeR!!!
```

**Console++** adds a bit of sparkling power to your shy little console.
It's not a fancy logging library with all the bells and whistles - it's a
"poor man" logger that you can drop in your code without having to rewrite it.

_Here is for the lazy developer!_

## How do I use it?

Ehm, like a `console` genius! Just type stuff like:

```javascript
console.log("A (boring) console.log message");

console.debug("An (irrelevant) console.debug message");

console.info("A (somewhat important) console.info message");

console.warn("A (quite important) console.warning message");

console.error("A (critical!) console.error message");
```

and you get:
<img src="1" />

## No really, how?

Yes, it manipulates the `console` object (_oh, the horror!_) so that you can
have some fancy colours, timestamped messages and a bit more. Output looks like:

```
[LEVEL - TIMESTAMP] THE_MESSAGE
```

Not all messages are printed. It introduces the concept of `level` (set via
`console.setLevel(level)`): as you would expect, it goes from `DEBUG` (lowest,
that corresponds to _print all the things_) to `ERROR` (highest, that
corresponds to _print only the errors_).

By default the `LEVEL` portion of the message is coloured (see below how
to disable this). Also, you can enable matching colouring for `THE_MESSAGE`
(see methods listing below).

One nifty feature (I think) it's that you have fine-grained control over
`THE_MESSAGE`. You can wrap text within `#COLOR{TEXT_TO_COLOR}` like:

```javascript
var message = "#red{this} is #cyan{a} #yellow{nice} message";
console.debug(message);
```

to print something like:
<img src="2" />

**PLEASE**, do read the code to learn more.

## How do I configure it?

**Console++** adds some few little methods to the `console` so you can tune
it a bit, based on your taste.

I'd like to be very lazy and say _"go read the code"_, but I guess I can list
here those methods.

```javascript```
console.LEVELS  = _LEVELS;

// Set/Get Level
console.setLevel(level);                //< default `DEBUG`
console.getLevel();
console.getLevelName(level);
console.getLevelColor(level);
console.isLevelVisible(levelToCompare);

// Enable/Disable Colored Output
console.enableColor();                  //< default enabled
console.disableColor();
console.isColored();

// Enable/Disable Colored Message Output
console.enableMessageColor();           //< default disabled
console.disableMessageColor();
console.isMessageColored();

// Enable/Disable Timestamped Output
console.enableTimestamp();              //< default enabled
console.disableTimestamp();
console.isTimestamped();

// Set OnOutput Callback (useful to write to file or something)
// Callback: `function(formattedMessage, levelName)`
console.onOutput(callback);             //< default `null`
```
