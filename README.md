# KeyEvent

Simply put, a cross-browser compatible set of constants for all of the different key codes that 
handled in HTML `keypress`, `keydown`, and `keyup` events.  Make your event code readable.

## Prerequisites

None.

## Installation

Include the `src/keyevent.js` in your project.

Here's a very very crude example.  Fit this properly into your project.
```
<html>
  <head>...</head>
  <body>
    Some page...
    ...
    <script type="text/javascript" src="[PATH_TO]/keyevent.js"></script>
    ...
  </body>
</html>
```

## What Do I Get?

An object named `KeyEvent` that has a bunch of constants.  For example: `KeyEvent.DOM_VK_RETURN` 
or `KeyEvent.DOM_VK_ESCAPE`, etc.  Check out the `src/keyevent.js`  It is quite trivial.

### NPM

```
npm install --save keyevent
```

or 

```
npm install --save-dev keyevent
```

Then simply include the `node_modules/keyevent/src/keyevent.js` in your HTML page/project.

### Bower (this will continue to exist, but I'm using NPM instead)

You can install KeyEvent using bower.

```
bower install keyevent
```

Then simply include the `bower_components/keyevent/src/keyevent.js` in your HTML page/project.

## Example Usage

Using jQuery's event binding, here's a couple simple cross-browser compliant ways of handling key events.

### Escape Clears Text Input Value

```
$('#some-text-input')
  .on('keypress', function (e) {
    if (e.keyCode === KeyEvent.DOM_VK_ESCAPE) {
      $(this).val('');
    }
  });
```

### Ctrl-Enter Submits The Inputs Form

```
$('#some-text-input')
  .off('keypress.ctrl-enter-return-submit')
  .on('keypress.ctrl-enter-return-submit', function (e) {
    if (e.ctrlKey) {
      switch (e.keyCode) {
        case KeyEvent.DOM_VK_RETURN:
        case KeyEvent.DOM_VK_ENTER:
          this.form.submit();
      }
    }
  });
```

## Useful Links

* [The Stack Overflow question that caused this...](http://stackoverflow.com/questions/1465374/javascript-event-keycode-constants/1465409#1465409)
