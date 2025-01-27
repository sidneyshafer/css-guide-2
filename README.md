# Guide to Learning More Advanced CSS3

>Snippets, examples, and code breakdowns for learning more advanced CSS3 concepts.

## Table of Contents
* [Targeted Selectors](#targeted-selectors)
    * [Direct Child Selectors](#direct-child-selectors)
    * [Adjacent Sibling Selector](#adjacent-sibling-selector)
    * [Attribute Selector](#attribute-selector)
    * [Attribute Value Selector](#attribute-value-selector)
* [The nth Child]()
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

<kbd><br>[Back to Top](#table-of-contents)<br></kbd>