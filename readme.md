# Prepopulated Address Fields
* By James Scariati
* May 2015

## Description
Request the user's location and then prepopulate their address in a form.

## Dependencies
* [jQuery](http://jquery.com)
* [Font Awesome](http://fontawesome.io) (for icons)
* Browser support for the [HTML5 Geolocation API](http://diveintohtml5.info/geolocation.html)
* Access to the [Google Maps JavaScript API](https://developers.google.com/maps/documentation/javascript/geocoding)

## Use
Include jQuery and the `jquery.prepopAddress.min.js` plugin in your HTML:

```javascript
<script src="lib/jquery.min.js"></script>
<script src="lib/jquery.prepopAddress.min.js"></script>
```

Add a form to your HTML with the four standard address fields (street address, city, state, and zip), along with a button to trigger the address population:

```html
<button id="prepop"><i class="fa fa-spin fa-gear"></i> Prefill My Address!</button>
<input type="text" id="street" name="street" placeholder="Number and street name" />
<input type="text" id="city" name="city" placeholder="City" />
<select id="state" name="state" class="blank">...</select>
<input type="text" id="zip" name="zip" placeholder="Zip Code" />
```

Then call `prepopAddress()` on the form:

```javascript
$(document).ready(function() {
	$("form").prepopAddress();
});
```

## Options

The following options are available:

```javascript
$("form").prepopAddress({
	buttonId: "prepop",
	streetInput: "street",
	cityInput: "city",
	stateInput: "state",
	zipInput: "zip"
});
```

All options are strings that set the IDs to use for the button and form fields. The values shown in the example above are the defaults, so you can omit the options if you use those exact IDs in your HTML.

## Notes

If more than one possible address is returned, only the first (and generally most accurate) result is used. The form fields are still editable, so the user can always correct a mistake manually if the service doesn't return a perfect match.