# semanticforms Changelog

## Next version

- Put your changes here...

## 3.0.3

- Fixed issue that prevented id selectors from allowing dots in the string.
- Fixed issue that prevented the clear field from dispatching an input event.

## 3.0.2

- Added support for a single checkbox rather than a group of checkboxes.

## 3.0.1

- Fixed alignment issue.

## 3.0.0

- Removed defualt two column layout. Now defaults to as many columns as the container is wide.
- Added `x2` class you can put on `dd` elements to double the width of a form. Does not apply on small screens.

## 2.1.2

- Added a function to the JS files's global scope called `semanticForms` that you can call to initialize new forms that have been added to the DOM since the initial initialization.
- Updated dependencies.

## 2.1.1

- Fixed a situation that could lead to a JS error.
- Fix minor alignment issue.

## 2.1.0

- Added all input types.
- Fixed clear field.
- Fixed markup mistakes in the examples.
- Fixed CSS to support `<menu>` elements correctly.
- Refactored the JavaScript to modernize it.
- Updated dependencies.

## 2.0.0

- Replaced `<div class="buttonGroup">` with a `<menu>` element. You will need to refactor your HTML accordingly.
- Fixed alignment issue caused by browser engines changing their alignment calculations since the first release.
- Various other refactoring.
- Pinned deps.
- Updated dependencies.

## 1.0.5

- Restricted JS events to target elements within `semanticForms` class form elements.
- Switched font sizes to % in case someone finds 16px too small and changes the default font size in the browser, these form fields will no longer stay fixed.
- Published to npm.
- Started CHANGELOG.
- Updated dependencies.

## 1.0.4 and below

[Here be dragons](https://en.wikipedia.org/wiki/Here_be_dragons)...
