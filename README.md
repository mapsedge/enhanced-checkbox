# enhanced-checkbox
A checkbox that returns a value even when it's not checked!

When you use a checkbox to indicate a Yes/No value, no value is sent with the form if the checkbox is unchecked. Since other controls - input:text, selects - send a name-value pair whether there's a value or not, that makes the checkbox an exception that must be handled, which means extra work!

This plug-in, written in vanilla javascript, transfers the behaviors of the checkbox to a hidden field that gets the desired control name, any attached classes, and one of two values based on the checked status (yes/no, true/false, 0/1, this/that). That way, checked or not, the form always sends a value.

This example uses a custom HTML element, but it could just as easily apply to any other HTML element.

USAGE

SCRIPT

var els = document.querySelectorAll('enh-checkbox');
els.forEach(el => {
	el.enhanced_checkbox({
			before_render: function () {
				// console.log('Custom after_render function');
			},
			after_render: function () {
				// console.log('Custom after_render function');
			},
     control: "hidden"
		});
});

HTML

<enh-checkbox name="pizza" value="pepperoni" title="bring on the cheese!" class="red-sauce"></enh-checkbox>

OUTPUT

<input type="checkbox" name="checkbox_u97bsi" title="bring on the cheese!"  class="red-sauce">
<input type="hidden" name="pizza" id="pizza" value="pepperoni">
