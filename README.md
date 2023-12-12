#work-in-progress

# enhanced-checkbox
A checkbox that returns a value even when it's not checked!

When you use a checkbox to indicate a Yes/No value, no value is sent with the form if the checkbox is unchecked. Since other controls - input:text, selects - send a name-value pair whether there's a value or not, that makes the checkbox an exception that must be handled, which means extra work!

This plug-in, written in vanilla javascript, transfers the behaviors of the checkbox to a hidden field that gets the desired control name, any attached classes, and one of two values based on the checked status (yes/no, true/false, 0/1, this/that). That way, checked or not, the form always sends a value.

This example uses a custom HTML element, but it could just as easily apply to any other HTML element.

Options *control*, *checked*, and *unchecked* can be passed through the options object in the function call, or set as attributes on the target control. If both are present, the attributes win.

<h2>USAGE</h2>

<h3>SCRIPT</h3>
<pre style="font-family: monospace">
var els = document.querySelectorAll('enh-checkbox');
els.forEach(el => {
	el.enhanced_checkbox({
			before_render: function () {
				// optional
			},
			after_render: function () {
				// optional
			},
     			control: "hidden", // default
			checked: 1, // default
			unchecked: 0, // default
		});
});
</pre>
<h3>HTML</h3>

<pre style="font-family: monospace">
&lt;!-- The checkbox will be checked if the checked attribute equals the value attribute -->
&lt;enh-checkbox name="lunch" value="pizza" title="bring on the cheese!" class="red-sauce" 
	checked="pizza" unchecked="burgers" 
	control="text">&lt;/enh-checkbox>
</pre>

<h3>OUTPUT</h3>

<pre style="font-family: monospace">
&lt;input type="checkbox" name="checkbox_something_random" title="bring on the cheese!"  class="red-sauce">
&lt;input type="text" name="lunch" id="lunch" value="pizza">
</pre>
