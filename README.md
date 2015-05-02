# zeroclipboard
Providing your users the ability to copy text to the clipboard can make your website much more convenient and valuable. Unfortunately Flash 10 broke most of the methods for doing so. Luckily a great library named ZeroClipboard exists. ZeroClipboard uses a pinch of Flash and touch of JavaScript to make copying to the clipboard happen.

# The Sample HTML
```javascript
<script type="text/javascript" src="ZeroClipboard.js"></script>
<textarea name="box-content" id="box-content" rows="5" cols="70">
	The David Walsh Blog is the best blog around!  MooTools FTW!
</textarea>
<br /><br />
<p><input type="button" id="copy" name="copy" value="Copy to Clipboard" /></p>
```
The above HTML features a form element with the ID "box-content" and a button with the ID "copy". Both of those element IDs will come into play with ZeroClipboard.

# The ZeroClipboard JavaScript
```javascript
//set path
ZeroClipboard.setMoviePath('ZeroClipboard.swf');
//create client
var clip = new ZeroClipboard.Client();
//event
clip.addEventListener('mousedown',function() {
	clip.setText(document.getElementById('box-content').value);
});
clip.addEventListener('complete',function(client,text) {
	alert('copied: ' + text);
});
//glue it to the button
clip.glue('copy');
```

With the ZeroClipboard object loaded we:
* Set the path to the SWF file.
* Create what ZeroClipboard calls a "client": A client is a single instance of the clipboard library on the page, linked to a particular button or other DOM element.
* Add a mousedown event listener that places text from inside our textarea into the clipboard.
* Add an optional complete event where we can add functionality to execute once the text has been successfully added to the clipboard.
* "Glue" the button to the functionality we've added in the steps above.

That's it! ZeroClipboard is an outstanding utility to allow copy to the clipboard functionality on any website.

#Thank to original auther
 Forked from [https://code.google.com/p/zeroclipboard/](zeroclipboard)

