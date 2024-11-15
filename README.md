# Semantic Forms

[![npm](https://img.shields.io/npm/v/semantic-forms.svg)](https://www.npmjs.com/package/semantic-forms)

A pattern library of forms based on semantic HTML enhanced with a modern UX.

See a [live demo here](https://kethinov.github.io/semanticforms/semanticForms.html).

# Usage

Include the `semanticForms.css` and `semanticForms.js` files from this repo into your project.

Then apply the `semanticForms` class to your `<form>` elements:

```html
<form class="semanticForms">
  <!-- your form here -->
</form>
```

Then the CSS/JS enhancements to your forms will apply automatically, assuming the markup structure you use is one of the supported patterns.

This library also monitors changes to the DOM and will enhance any additional `semanticForms` forms you insert, but the monitoring may not be perfect. If you want to re-scan for new forms to enhance manually, simply call `window.semanticForms()`.

# Features

Overview of pattern library features:

## Float label inputs

The float label input pattern is notoriously difficult to implement in a fashion that doesn't degrade HTML semantics or accessibility. This pattern library implements a solution that solves that problem. Your label doesn't need to be a sibling of your input like with other implementations. This implementation also has a custom clear field driven by SVG embedded in the CSS.

### Example

```html
<form class="semanticForms">
  <dl>
    <dt><label for="name">Name</label></dt>
    <dd><input id="name" name="name" type="text" placeholder="e.g. John Smith"></dd>
  </dl>
</form>
```

### Or with a `<textarea>`

```html
<form class="semanticForms">
  <dl>
    <dt><label for="textarea">Textarea</label></dt>
    <dd><textarea id="textarea" name="textarea" rows="5" cols="50" placeholder="e.g. Long string of text"></textarea></dd>
  </dl>
</form>
```

If you would like to manipulate the size of the area on the input field reserved for the click event of the clear field, apply one or both of the following `data-` attributes to your form:

Adjust the horizontal offset of the clear field's click event click area (the default is 21):

```html
<form class="semanticForms" data-clearfield-horizontal-offset="21">
  <!-- your form here -->
</form>
```

Adjust the vertical offset of the clear field's click event click area (the default is 5):

```html
<form class="semanticForms" data-clearfield-vertical-offset="5">
  <!-- your form here -->
</form>
```

If you want to double the width of the input field (on screens with the extra space), add a `x2` class to the `dd` element.

## Button groups

You can align buttons side-by-side, or in left/right/center groups.

### Non-grouped example

Nothing fancy here:

```html
<button type="submit" name="submit">Non-grouped submit button</button>
<button type="submit" name="submit">Another one</button>
```

### Button groups

Driven by flexbox to intelligently align the buttons based on how many are in the group:

```html
<!-- aligns left/right -->
<menu>
  <li><button type="submit" name="submit">Button 1</button></li>
  <li><button type="submit" name="submit">Button 2</button></li>
</menu>

<!-- aligns left/center/right -->
<menu>
  <li><button type="submit" name="submit">Button 1</button></li>
  <li><button type="submit" name="submit">Button 2</button></li>
  <li><button type="submit" name="submit">Button 3</button></li>
</menu>
```

## Checkboxes and radio buttons

Checkboxes and radio buttons need to follow the following markup structure:

### A single checkbox

Not too different than other inputs:

```html
<form class="semanticForms">
  <dl>
    <dt><label for="checkbox">Single checkbox</label></dt>
    <dd><input id="checkbox" name="checkbox" type="checkbox"></dd>
  </dl>
</form>
```

### Checkbox group

```html
<form class="semanticForms">
  <dl>
    <dt><label data-for="some_field_name">Checkboxes:</label></dt>
    <dd class="checkboxes">
      <ul id="some_field_name">
        <li><input type="checkbox" name="some_field_name" id="c_one"> <label for="c_one">One</label></li>
        <li><input type="checkbox" name="some_field_name" id="c_two"> <label for="c_two">Two</label></li>
        <li><input type="checkbox" name="some_field_name" id="c_three"> <label for="c_three">Three</label></li>
      </ul>
    </dd>
  </dl>
</form>
```
### Radio buttons

```html
<form class="semanticForms">
  <dl>
    <dt><label data-for="some_field_name">Radios:</label></dt>
    <dd class="radios">
      <ul id="some_field_name">
        <li><input type="radio" name="some_field_name" id="r_one"> <label for="r_one">One</label></li>
        <li><input type="radio" name="some_field_name" id="r_two"> <label for="r_two">Two</label></li>
        <li><input type="radio" name="some_field_name" id="r_three"> <label for="r_three">Three</label></li>
      </ul>
    </dd>
  </dl>
</form>
```

## Other features

- Custom-styled select boxes with a custom drawn arrow graphic driven by SVG embedded in the CSS.
- Custom-styled submit buttons to match the aesthetic of the custom-styled forms.
- Responsive: on wide screens, the forms split into multiple columns. On smaller screens, they collapse to a single column.
- Dark mode: apply an additional class of `dark` to your `<form>` elements to use the dark mode.
- Low-flow mode that displays on old browsers, JS-disabled browsers, or can be activated manually by adding the `lowFlow` class to your `<form>` element. The low-flow mode reverts the float label pattern to traditional labels and collapses the forms to single column mode, but preserves the other visual design enhancements driven purely by CSS.

See `semanticForms.html` or the [live demo](https://kethinov.github.io/semanticforms/semanticForms.html) for a full demo of all the markup patterns.

# Contributing

- Fork/clone this repo.
- `npm ci`
- Make your changes. If you want to alter the CSS, do the changes in the `.less` files.
- `npm run build`. The build step compiles the LESS file into CSS.
- Test your changes by opening `semanticForms.html` in your browser.
- Commit, push, open pull request.
