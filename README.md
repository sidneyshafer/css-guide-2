# Guide to Learning More Advanced CSS3

>Snippets, examples, and code breakdowns for learning more advanced CSS3 concepts.

## Table of Contents
* **[Targeted Selectors](#targeted-selectors)**
    * [Direct Child Selectors](#direct-child-selectors)
    * [Adjacent Sibling Selector](#adjacent-sibling-selector)
    * [Attribute Selector](#attribute-selector)
    * [Attribute Value Selector](#attribute-value-selector)
* **[The nth Child](#the-nth-child)**
    * [First Child Selector](#first-child-selector)
    * [Last Child Selector](#last-child-selector)
    * [nth Child Selectors](#nth-child-selectors)
* **[Before and After](#before-and-after)**
    * [Overview of Before and After](#overview-of-before-and-after)
    * [Element Placement](#element-placement)
    * [The Content Property](#the-content-property)
    * [Key Points](#key-points)
    * [Code Examples](#code-examples)
* **[Box Shadows](#box-shadows)**
    * [Box Shadow Property Syntax](#box-shadow-property-syntax)
    * [Code Examples](#box-shadow-code-examples)
* **[Text Shadows](#text-shadows)**
    * [Text Shadow Property Syntax](#text-shadow-property-syntax)
    * [Code Examples](#text-shadow-code-examples)
* **[CSS Variables](#css-variables)**
    * [Overview of CSS Variables](#overview-of-css-variables)
    * [Defining Variables](#defining-variables)
    * [Using Variables](#using-variables)
    * [Advantages of using Custom Properties](#advantages-of-using-custom-properties)
* **[Keyframes]()**
* **[Transitions]()**
* **[Transform]()**

---

## Targeted Selectors

* [Direct Child Selectors](#direct-child-selectors)
* [Adjacent Sibling Selector](#adjacent-sibling-selector)
* [Attribute Selector](#attribute-selector)
* [Attribute Value Selector](#attribute-value-selector)

### Direct Child Selectors
```css
div > p {
    background: #ddd;
}
```
* The direct child selector targets immediate child elements with the use of `>`.
* This example targets all `<p>` elements that are **direct children** of a `<div>`. Only `<p>` elements immediately inside a `<div>` will be styled with a background color of `#ddd`.

### Adjacent Sibling Selector
```css
div + p {
   background: #333;
   color: #fff;
}
```
* The adjacent sibling selector targets an element immediately following a specific sibling (`+`).
* This example targets the immediate sibling `<p>` element that directly follows a `<div>`. The `<p>` immediately after the `<div>` in will have a background color of `#333` and white (`#fff`) text color. Any `<p>` elements not directly after a `<div>` are not affected.

### Attribute Selector
```css
a[target] {
   background: #ff0000;
   color: #fff;
}
```
* The attribute selector targets elements with a specific attribute, using the syntax `[attr]`.
* This example targets all `<a>` elements that have a `target` attribute.

### Attribute Value Selector
```css
input[type='text'],
input[type='email'] {
   width: 100%;
   margin-bottom: 5px;
}
```
* The attribute value selector targets elements with a specific attribute and value, following the syntax `[attr='value']`.
* Often used for styling form input and label elements.
* This example targets `<input>` elements with a type attribute value of `'text'` or `'email'`.

### Targeted Selector Summary
| Selector              | Overview                         | Syntax |
| --------------------- | -------------------------------- | -------------- |
| Direct Child Selector | Targets immediate child elements | `>` |
| Adjacent Sibling Selector | Targets an element immediately following a specific sibling | `+` |
| Attribute Selector | Targets elements with a specific attribute | `[attr]` |
| Attribute Value Selector | Targets elements with a specific attribute and value | `[attr='value']` |

> [!NOTE]
>See full source code for this section in [01-targeted-selectors.html](/src/01-targeted-selectors.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

---

## The nth Child

* [First Child Selector](#first-child-selector)
* [Last Child Selector](#last-child-selector)
* [nth Child Selectors](#nth-child-selectors)

### First Child Selector
```css
li:first-child {
   background: red;
}
```
* Targets the **first child** of its parent element.
* In this example, the first `<li>` in the `<ul>` list is styled with a red background.

### Last Child Selector
```css
li:last-child {
   background: red;
}
```
* Targets the **last child** of its parent element.
* In this example, the last `<li>` in the `<ul>` list is styled with a red background.

### nth Child Selectors

**nth Child Formula**
* `a*n + b`:
    * `a` determines the interval
    * `b` shifts the starting point
    * `n` represents the integer

**Example 1:**
```css
li:nth-child(5) {
   background: purple;
}
```
* Targets the **5th child** of its parent element.
* In this example, the 5th `<li>` element is styled with a purple background.

**Example 2:**
```css
li:nth-child(3n+0) {
   background: orange;
}
```
* Targets every **3rd child**, starting from the 1st element (element `0`) of its parent.
* Formula Breakdown:
    * `n` is represented as an integer.
    * Positions are computed as: `3*0+0`, `3*1+0`, `3*2+0`, etc.
    * Result positions would follow as: 3, 6, 8, 12, etc., which are targeted to have an orange background.

**Example 3:**
```css
li:nth-child(3n+7) {
   background: yellow;
}
```
* Targets every **3rd child**, starting from the 7th element of its parent.
* Formula follow the previous example, except starting from position 7 in the list:
    * `3*0+7`, `3*1+7`, `3*2+7`, etc.

**Example 4:**
* Using the `odd` keyword.
```css
li:nth-child(odd) {
   background: #ccc;
}
```
* Targets every odd-numbered child.
* `odd` is equivalent to the formula `2n+1`.

**Example 5:**
* Using the `even` keyword.
```css
li:nth-child(even) {
   background: #ddd;
}
```
* Targets every even-numbered child.
* `even` is equivalent to the formula `2n`. 

> [!NOTE]
>See full source code for this section in [02-nth-child.html](/src/02-nth-child.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

---

## Before and After
* [Overview of Before and After](#overview-of-before-and-after)
* [Element Placement](#element-placement)
* [The Content Property](#the-content-property)
* [Key Points](#key-points)
* [Code Examples](#code-examples)

### Overview of Before and After

The `:before` and `:after` **pseudo-elements** allow you to insert content before or after the content of an element. 

They are widely used for adding decorative elements, icons, or extra styling without adding more elements to the HTML.

### Element Placement
* `:before` places content **before** an element's main content.
* `:after` places content **after** an element's main content.

### The Content Property
* The `content` property is mandatory for the pseudo-elements to render.
* The property can hold text, unicode characters, or in most cases an empty string (`content: '';`).

### Key Points
* `:before` and `:after` can be styled like any other element, using color, background, position, etc.
* They do not impact the **document flow**; these pseudo-elements are independent layers.

### Code Examples
```css
header:before {
    content: '';
    background: url('img/mountain.jpg') no-repeat center center/cover;
    opacity: 0.4;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
}
```
* This example adds a decorative background image to the `header` element with the use of `:before`.

```css
.is-required:after {
   content: '*';
   color: red;
   padding-left: 2px;
}
```
* With the use of `:after`, this example adds a red asterisk (`*`) after elements with the class `is-required`.
* This is often used to indicate mandatory fields in forms.

> [!NOTE]
>See full source code for this section in [03-before-after.html](/src/03-before-after.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

---

## Box Shadows

* [Box Shadow Property Syntax](#box-shadow-property-syntax)
* [Code Examples](#box-shadow-code-examples)

### Box Shadow Property Syntax
```css
box-shadow: [inset] offset-x offset-y [blur-radius] [spread-radius] color;
```
1. `inset` (*optional*)
    * If specified, the shadow appears **inside** the element.
    * If omitted, the shadow appears **outside** the element.
2. `offset-x` (*required*)
    * Specifies the **horizontal** shadow position.
    * Positive values move the shadow to the right.
    * Negative values move the shadow to the left.
3. `offset-y` (*required*)
    * Specifies the **vertical** shadow position.
    * Positive values move the shadow down.
    * Negative values move the shadow up.
4. `blur-radius` (*optional*)
    * Controls the blur of the shadow.
    * Higher values make the shadow softer.
    * Default value is `0`.
5. `spread-radius` (*optional*)
    * Controls the size of the shadow.
    * Positive values increase the shadow's size.
    * Negative values shrink it.
6. `color` (*required*)
    * Defines the shadow's color.
    * Accepts any CSS color format.

**Multiple Shadows:**
* You can specify multiple shadows, separated by commas within the `box-shadow` property.

---

### Box Shadow Code Examples

**Example 1:**
```css
box-shadow: 10px 10px teal;
```
* Sets the shadow `10px` to the right and `10px` down.
* No blur or spread is applied, so the shadow has sharp edges.
* Shadow color is specified as `teal`.

---

**Example 2:**
```css
box-shadow: 10px 10px 20px teal;
```
* Same as **Example 1**, but adds a `20px` blur radius, making the shadow softer.

---

**Example 3:**
```css
box-shadow: -5px -5px 20px teal;
```
* Sets the shadow `5px` to the left and `5px` up, with as `20px` blur radius and a shadow color of `teal`.

---

**Example 4:**
```css
box-shadow: inset -3px -3px teal;
```
* Using the `inset` keyword makes the shadow appear inside the box.

---

**Example 5:**
```css
box-shadow: 3px 3px 5px teal, -3px -3px 5px olive;
```
* This example adds two shadows separated by a comma.

> [!NOTE]
>See full source code for this section in [04-box-shadows.html](/src/04-box-shadows.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

---

## Text Shadows

* [Text Shadow Property Syntax](#text-shadow-property-syntax)
* [Code Examples](#text-shadow-code-examples)

### Text Shadow Property Syntax
```css
text-shadow: h-shadow v-shadow [blur-radius] [color];
```
1. `h-shadow` (Horizontal Shadow - *required*)
    * Specifies the **horizontal** position of the shadow.
    * Positive values move the shadow to the right.
    * Negative values move the shadow to the left.
2. `v-shadow` (Vertical Shadow - *required*)
    * Specifies the **vertical** position of the shadow.
    * Positive values move the shadow downward.
    * Negative values move the shadow upward.
3. `blur-radius` (*optional*)
    * Controls the blur of the shadow.
    * Higher values make the shadow softer.
    * Default value is `0`.
4. `color` (*optional*)
    * Defines the shadow's color.
    * Accepts any CSS color format.

**Multiple Shadows:**
* You can specify multiple shadows, separated by commas within the `text-shadow` property.

---

## Text Shadow Code Examples

**Example 1:**
```css
text-shadow: 0.2rem 0.2rem steelblue;
```
* The shadow is offset `0.2rem` to the right (horizontal).
* The shadow is offset `0.2rem` downward (vertical).
* The shadow color is `steelblue`.

**Example 2:**
```css
text-shadow: 0.4rem 0.3rem 0.7rem steelblue;
```
* The shadow is offset `0.4rem` to the right (horizontal).
* The shadow is offset `0.3rem` downward (vertical).
* The shadow has a blur radius of `0.7rem`.
* The shadow color is `steelblue`.

**Example 3:**
```css
text-shadow: -0.4rem -0.3rem 0.7rem steelblue;
```
* The shadow is offset `-0.4rem` to the left (horizontal).
* The shadow is offset `-0.3rem` upward (vertical).
* The shadow has a blur radius of `0.7rem`.
* The shadow color is `steelblue`.

> [!NOTE]
>See full source code for this section in [05-text-shadows.html](/src/05-text-shadows.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

---

## CSS Variables

* [Overview of CSS Variables](#overview-of-css-variables)
* [Defining Variables](#defining-variables)
* [Using Variables](#using-variables)
* [Advantages of using Custom Properties](#advantages-of-using-custom-properties)

---

### Overview of CSS Variables

* CSS variables, also known as **custom properties**, are a way to store reusable values in CSS stylesheets.
* The variables use a prefix of two dashes `--` and are declared inside a selector, typically `:root` for global scope.
* They can be used throughout the stylesheet with the `var()` function.

> [!TIP]
>The [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties) provides excellent information about using CSS custom properties.

---

### Defining Variables
* Variables are often defined in the `:root` selector for access anywhere in the stylesheet:
```css
:root {
   --max-width: 1100px;
   --primary-color: steelblue;
   --secondary-color: skyblue;
   --light-color: #f4f4f4;
   --box-1-width: 1;
   --box-2-width: 2;
}
```

---

### Using Variables
* Variables are accessed using the `var()` function:
```css
header {
    background-color: var(--primary-color);
    border-bottom: 5px var(--secondary-color) solid;
}
```
> [!NOTE]
>The `var()` function supports fallback values if the variable isn't defined.

---

### Advantages of using Custom Properties
* **Reusability:**
    * Define a value once and reuse it across your stylesheet.
    * Easy to update multiple styles by changing the variable in one place.
* **Consistency:**
    * Colors, sizes, and other repeated values are stored in variables for consistency across the design.
* **Maintainability/Dynamic Updates:**
    * Updating a single variable changes all elements using it.
    * Variables can be updated based on different contexts, such as themes or media queries.
* **Scoped Declaration:**
    * Variables can be scoped to a specific selector and won't affect other parts of the stylesheet.
* **Scalability:**
    * You can easily add more variables for other design elements as needed.

> [!NOTE]
>See full source code for this section in [06-variables.html](/src/06-variables.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

---