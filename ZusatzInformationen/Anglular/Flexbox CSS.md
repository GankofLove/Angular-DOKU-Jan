
# Flexbox

Link: https://css-tricks.com/snippets/css/a-guide-to-flexbox/


## display

This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

Note that CSS columns have no effect on a flex container.

```css
.container {
  display: flex; /* or inline-flex */
}
```
<br>

## order

By default, flex items are laid out in the source order. However, the order property controls the order in which they appear in the flex container.

```css
.item {
  order: 5; /* default is 0 */
}
```
Items with the same order revert to source order.

<br>

## flex-direction

This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is (aside from optional wrapping) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.
```css
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```
row (default): left to right in ltr; right to left in rtl
row-reverse: right to left in ltr; left to right in rtl
column: same as row but top to bottom
column-reverse: same as row-reverse but bottom to top

<br>

## flex-grow
two rows of items, the first has all equally-sized items with equal flex-grow numbers, the second with the center item at twice the width because its value is 2 instead of 1.

This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

If all items have flex-grow set to 1, the remaining space in the container will be distributed equally to all children. If one of the children has a value of 2, that child would take up twice as much of the space either one of the others (or it will try, at least).

```css
.item {
  flex-grow: 4; /* default 0 */
}
```
Negative numbers are invalid.


![Alt text](/assets/felxbox.png)
