# jQuery FullScreen Plugin

A jQuery 1.7 plugin that wraps around the *[Full Screen API](https://developer.mozilla.org/en/DOM/Using_full-screen_mode)* and works around various browser differences. Works in FF 10, Chrome and Safari. It is useful for presenting users with an easier to read version of your web pages, or zooming *&lt;canvas&gt;* and *&lt;video&gt;* elements.

## How to use

Include jquery.fullscreen.js in your page along with version 1.7 of the jQuery library. This gives you the `$('#elem').fullScreen()` method. You can optionally pass an object with properties:

<table>
	<tr>
		<th>Property</th>
		<th>Value</th>
		<th>Meaning</th>
	</tr>
    <tr>
        <td>background</td>
        <td>a color hash</td>
        <td>This is the color that will be used for the background.</td>
    </tr>
    <tr>
        <td>callback</td>
        <td>a function</td>
        <td>The callback function will be called on a full screen change event. It has one argument - a boolean indicating whether we are in full screen or not.</td>
    </tr>
    <tr>
    	<td>fullscreenClass</td>
    	<td>a string</td>
    	<td>This is the CSS class that will be added to elements in fullscreen mode. The default class is "fullScreen".</td>
    </tr>
</table>

After the plugin makes your element full screen, it will add the `fullScreen` class on it (unless overridden with the `fullscreenClass` parameter), so you can easily style it.

## Example

```js
// The plugin sets the $.support.fullscreen flag:
if($.support.fullscreen){
	
	// ...
	// Show your full screen button here
	// ...
	
	$('#fullScreen').click(function(e){
	
		$('#content').fullScreen();
		
		// You can also pass a hash with properties:
		// $('#content').fullScreen({
		//	'background'	: '#111',
		//	'callback'		: function(isFullScreen){
		//		// ...
		//		// Do some cleaning up here
		//		// ...
		//	}
		// });
	});
}
```

You can then apply additional styles to your element. Take the opportunity to increase the font size, hide distractions and make for a better reading experience.

```css

#content.fullScreen{
	/* Give the element a width and margin:0 auto; to center it. */
}

```

If you later wish **to cancel the full screen view**, you can do so by calling the `fullScreen()` method again.

## Demo

Go to [Tutorialzine](http://tutorialzine.com/2012/02/enhance-your-website-fullscreen-api/) for a live demo.
