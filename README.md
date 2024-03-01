# MapBuhneVorauswahl.html
 Adjust the content as necessary to fit your project's specifics.

---

# Interactive Image Mapping Feature

## Overview
This interactive image mapping feature enables users to select specific areas on an image by clicking on them. It's designed for use within surveys to allow respondents to identify locations or points of interest within a given image. This README outlines the setup process and provides examples of how to implement the feature in your projects.

## Setup
To set up the interactive image mapping feature in your project, follow these steps:

1. **HTML Structure**: Include the HTML code for the main container, image container, marker, and clickable areas (defined by `<area>` tags within a `<map>` element).

2. **JavaScript Functionality**: Ensure the JavaScript code for handling events (e.g., city and venue dropdown changes, image clicks to set markers) is included in your project. The JavaScript code is responsible for hiding position questions, updating images based on selected venues, and positioning markers on the image.

3. **Styling**: Add the CSS styles to position the image container, image, and marker correctly.

## Dependencies
This feature is dependent on the selection made in the `cityDropdown`. Changing the city updates the venue dropdown and the displayed image accordingly.

### Example
```html
<!-- Assuming the cityDropdown has an ID of 'answer332186X96X4036' -->
<select id="answer332186X96X4036">
  <option value="B">Berlin</option>
  <option value="HH">Hamburg</option>
  <option value="M">München</option>
</select>
```
When a city is selected, the corresponding venue and image are automatically updated.

## Condition in Survey Admin
To ensure the image question appears only when a city has been selected, use the following condition in your survey admin settings:
```
(!is_empty(city.NAOK))
```
This condition checks that the city field is not empty before displaying the image question.

## Function Examples

### `setMarker()`
This function positions and displays a marker on the image where the user clicks.
```javascript
image.addEventListener('click', function(event) {
  setMarker(event);
});
```

### `updateImage()`
Updates the displayed image based on the selected venue.
```javascript
venueDropdown.addEventListener('change', updateImage);
```

### Dependency Example: `cityDropdown` Change Listener
Listens for changes on the `cityDropdown` to update the venue dropdown and image.
```javascript
cityDropdown.addEventListener('change', function() {
  // Code to update venueDropdown and image
});
```


