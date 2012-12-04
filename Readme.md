
# Confirmation

  A version of the [uikit dialog box](https://github.com/component/dialog) written in pure javascript, with structural styling. This widget is useful for requesting confirmation in deleting or altering important information. For embedding html into a dialog, try `bmcmahen/modal`. 

## Installation
		
		$ npm install -g component
		$ cd myComponents
    $ component install bmcmahen/confirmation

## Events

* `show` the dialog is shown. 
* `hide` the dialog is set to hide. 
* `hidden` the dialogue is hidden after the (optional) animation.
* `cancel` the (optional) cancel button was pressed.
* `okay` the (optional) okay button was pressed.

## API

### confirmation([attributes],[options])
With the default template, attributes available include:
```javascript
confirmation({
	title: 'your title',
	content: 'your content',
	okay: 'your okay button text',
	cancel: 'your cancel button text'
});
```

If you precompile your own template and pass it into the options attribute you can also include any additional attributes that are contained within your template. 

### confirmation#show()

Show dialog. 

### confirmation#hide()

Hide dialog.

### confirmation#effect

Include it before `show()` to animate it. Options include `slide`, `fade`, and `scale`. 

### confirmation#okay(event)

Is called when the `okay button` is pressed. Example:
```javascript
confirmation({okay: 'okay'}).ok(function(e){ console.log('okay was pressed ')});
```

### confirmation#cancel(event)

Same as confirmation#okay, except for the `cancel` button.

### confirmation#addClass(name)

Add a class name to the dialog. 

## Example

```javascript
var c = require('confirmation');

var trigger = document.querySelector('button')
	, confirmation; 

trigger.onclick = function(){
	confirmation = c({
		title: 'hi',
		content: 'hello',
		cancel: 'Cancel',
		okay: 'Delete'
	}).effect('fade')
		.show()
		.okay(function(e){
			console.log('Delete it.');
		})
		.cancel(function(e){
			console.log('cancel it.');
		}); 
};
```


## License

  MIT
