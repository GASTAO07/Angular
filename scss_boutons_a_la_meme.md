
```
To make all buttons the same size, you can add fixed `width` and `height` properties to your `.button-degrade` class in your CSS. Here's how you might do it:

```css
.button-degrade {
  /* existing properties... */

  width: 150px;  /* adjust as needed */
  height: 50px;  /* adjust as needed */
}
```
This will make all buttons with the class `.button-degrade` have the same width and height. Adjust the pixel values as needed to fit your design.

Note, however, that if your button text is long and the button width is too small, the text might overflow out of the button. To prevent this, you might want to add some padding and allow the button to resize to fit its content:

```css
.button-degrade {
  /* existing properties... */

  padding: 10px 20px;  /* adjust as needed */
  min-width: 150px;  /* adjust as needed */
}
```
In this case, all buttons will have at least the specified width, but they will expand if their content is too wide.
```
