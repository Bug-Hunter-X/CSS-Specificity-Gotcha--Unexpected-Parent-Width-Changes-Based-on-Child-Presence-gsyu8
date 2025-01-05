# CSS Specificity Gotcha: Unexpected Parent Width Changes Based on Child Presence

This repository demonstrates a subtle CSS specificity issue where the width of a parent container changes unexpectedly depending on the presence of a child element.  The bug arises from the interaction between two CSS rules targeting the same element, one with higher specificity.

## The Bug

The `bug.css` file contains the following CSS rules:

```css
.container { width: 80%; }
.container .item { width: 50%; }
```

When an element with the class `item` is present inside an element with the class `container`, the `width` of `.container` is implicitly affected due to the higher specificity of the `.container .item` selector, even though it only sets the width of the child.

## The Solution

The solution is to use more sophisticated CSS techniques to manage width consistently, regardless of the presence of child elements. `bugSolution.css` provides a possible solution.  See below for details.

## Solution Details
The `bugSolution.css` file introduces a flexible solution. Depending on your specific design requirements, several approaches could work. One possible solution could be to use more precise selectors or ensure that the styles of `.container` and `.container .item` are mutually non-interfering. 