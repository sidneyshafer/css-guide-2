# Guide to Learning More Advanced CSS3

>Snippets, examples, and code breakdowns for learning more advanced CSS3 concepts.

## Table of Contents
* [Targeted Selectors](#targeted-selectors)
    * [Direct Child Selectors](#direct-child-selectors)
    * [Adjacent Sibling Selector](#adjacent-sibling-selector)
    * [Attribute Selector](#attribute-selector)
    * [Attribute Value Selector](#attribute-value-selector)
* [The nth Child](#the-nth-child)
    * [First Child Selector](#first-child-selector)
    * [Last Child Selector](#last-child-selector)
    * [nth Child Selectors](#nth-child-selectors)
* [Before and After]()
* [Box Shadows]()
* [Text Shadows]()
* [CSS Variables]()
* [Keyframes]()
* [Transitions]()
* [Transform]()

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

>See full source code for this section in [01-targeted-selectors.html](/src/01-targeted-selectors.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>

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

>See full source code for this section in [02-nth-child.html](/src/02-nth-child.html)

<kbd> <br> [Back to Top](#table-of-contents) <br> </kbd>