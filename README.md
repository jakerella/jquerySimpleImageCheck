jQuery SimpleImageCheck
----


SimpleImageCheck is a
<a href='http://plugins.jquery.com/project/simpleImageCheck' title='Go to the jQuery plug-in page'>jQuery plug-in</a>
that makes custom image checkboxes and radio buttons super easy.
Simply use standard inputs and labels for your fields, then call
the function to set up the custom UI. Your checkbox (or radio button)
is still there (just hidden), and all form submissions will work as normal.

**Requires jQuery 1.2+**

**Feature List**

* Use custom images for checkboxes and radio buttons
* Continue to use standards-compliant input fields and labels
* Doesn't break form submission
* Full ARIA implementation
* Lightweight (1.93kb minified)

**Tested Browsers**

* Firefox 3+
* Internet Explorer 7+
* Chrome
* Opera

**Usage**

_Options:_

```js
{
    image: String,          // (REQUIRED) The image source to show when the checkbox IS NOT checked.
    imageChecked: String,   // (REQUIRED) The image source to show when the checkbox IS checked.
    afterCheck: Function    // Optional callback function for when the image/checkbox
                            // is toggled. The single argument is a boolean indicating
                            // the state of the checkbox.
}
```

_Simple Case:_

```html
<label for='someCheckbox'>Check it?</label>
<input type='checkbox' id='someCheckbox' />
```

```js    
$('#someCheckbox').simpleImageCheck({
  image: 'unchecked.png',
  imageChecked: 'checked.png',
  afterCheck: function(isChecked) {
    // do something based on boolean value: isChecked
  }
});
```

You can find [some examples](http://jordankasper.com/jquery/imagecheck) on my personal site.

**Known Issues**

1. IE 6 doesn't like my examples page...
1. All versions of IE (that I tested) have an issue when you attach a "change" event handler to the input node (otherwise you're fine). You will have to click on the image/checkbox multiple times in order to "tick" the box.

WORKAROUND for #2: In order to get around this issue, you can use the "afterCheck" event handler option when instantiating the simpleImageCheck plugin:

```js
$('#myCheckbox').simpleImageCheck({
  image: 'unchecked.png',
  imageChecked: 'check.png',
  afterCheck: function(isChecked) {
    if (isChecked) {
      // do something
    }
  }
});
```
