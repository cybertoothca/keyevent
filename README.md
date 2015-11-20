# KeyEvent

Simply put, a cross-browser compatible set of constants for all of the different key codes that 
handled in HTML `keypress`, `keydown`, and `keyup` events.

## Prerequisites

None.

## Installation

Include the `keyevent.js` in your HTML page or project.

    <html>
      <head>...</head>
      <body>
        Some page...
        ...
        <script type="text/javascript" src="[PATH_TO]/keyevent.js"></script>
        ...
      </body>
    </html>

### Bower

You can install KeyEvent using bower.

    $ bower install keyevent

Then simply include the `bower_components/keyevent.js` in your HTML page/project.

## Examples

Using jQuery's event binding, here's a couple simple cross-browser compliant ways of handling key events.

### Escape Clears Text Input Value

    $('#some-text-input')
      .on('keypress', function (e) {
        if (e.keyCode === KeyEvent.DOM_VK_ESCAPE) {
          $(this).val('');
        }
      });

### Ctrl-Enter Submits The Inputs Form

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

## Useful Links

* [The Stack Overflow question that caused this...](http://stackoverflow.com/questions/1465374/javascript-event-keycode-constants/1465409#1465409)

