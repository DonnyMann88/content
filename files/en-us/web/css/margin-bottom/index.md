---
title: margin-bottom
slug: Web/CSS/margin-bottom
page-type: css-property
browser-compat: css.properties.margin-bottom
sidebar: cssref
---

The **`margin-bottom`** [CSS](/en-US/docs/Web/CSS) property sets the [margin area](/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model#margin_area) on the bottom of an element. A positive value places it farther from its neighbors, while a negative value places it closer.

{{InteractiveExample("CSS Demo: margin-bottom")}}

```css interactive-example-choice
margin-bottom: 1em;
```

```css interactive-example-choice
margin-bottom: 10%;
```

```css interactive-example-choice
margin-bottom: 10px;
```

```css interactive-example-choice
margin-bottom: 0;
```

```html interactive-example
<section id="default-example">
  <div id="container">
    <div class="row"></div>
    <div class="row transition-all" id="example-element"></div>
    <div class="row"></div>
  </div>
</section>
```

```css interactive-example
#container {
  width: 300px;
  height: 200px;
  display: flex;
  align-content: flex-start;
  flex-direction: column;
  justify-content: flex-start;
}

.row {
  height: 33.33%;
  display: inline-block;
  border: solid #ce7777 10px;
  background-color: #2b3a55;
  flex-shrink: 0;
}

#example-element {
  border: solid 10px #ffbf00;
  background-color: #2b3a55;
}
```

![The effect of the CSS margin-bottom property on the element box](margin-bottom.svg)

This property has no effect on _non-[replaced](/en-US/docs/Glossary/Replaced_elements)_ inline elements, such as {{HTMLElement("span")}} or {{HTMLElement("code")}}.

## Syntax

```css
/* <length> values */
margin-bottom: 10px; /* An absolute length */
margin-bottom: 1em; /* relative to the text size */
margin-bottom: 5%; /* relative to the nearest block container's width */
margin-bottom: anchor-size(width);
margin-bottom: calc(anchor-size(--myAnchor self-block, 20px) / 3);

/* Keyword values */
margin-bottom: auto;

/* Global values */
margin-bottom: inherit;
margin-bottom: initial;
margin-bottom: revert;
margin-bottom: revert-layer;
margin-bottom: unset;
```

The `margin-bottom` property is specified as the keyword `auto`, or a `<length>`, or a `<percentage>`. Its value can be positive, zero, or negative.

### Values

- {{cssxref("&lt;length&gt;")}}
  - : The size of the margin as a fixed value.
    - For _anchor-positioned elements_, the {{cssxref("anchor-size()")}} function resolves to a {{cssxref("&lt;length&gt;")}} value relative to the associated _anchor element_'s width or height (see [Setting element margin based on anchor size](/en-US/docs/Web/CSS/CSS_anchor_positioning/Using#setting_element_margin_based_on_anchor_size)).

- {{cssxref("&lt;percentage&gt;")}}
  - : The size of the margin as a percentage, relative to the inline size (_width_ in a horizontal language, defined by {{cssxref("writing-mode")}}) of the [containing block](/en-US/docs/Web/CSS/CSS_display/Containing_block).
- `auto`
  - : The browser selects a suitable value to use. See {{cssxref("margin")}}.

## Formal definition

{{cssinfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Setting positive and negative bottom margins

#### HTML

```html
<div class="container">
  <div class="box0">Box 0</div>
  <div class="box1">Box 1</div>
  <div class="box2">Box one's negative margin pulls me up</div>
</div>
```

#### CSS

CSS for divs to set margin-bottom and height

```css
.box0 {
  margin-bottom: 1em;
  height: 3em;
}
.box1 {
  margin-bottom: -1.5em;
  height: 4em;
}
.box2 {
  border: 1px dashed black;
  border-width: 1px 0;
  margin-bottom: 2em;
}
```

Some definitions for container and divs so margins' effects can be seen more clearly

```css
.container {
  background-color: orange;
  width: 320px;
  border: 1px solid black;
}
div {
  width: 320px;
  background-color: gold;
}
```

#### Result

{{ EmbedLiveSample('Setting_positive_and_negative_bottom_margins',350,200) }}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{cssxref("margin-top")}}, {{cssxref("margin-right")}}, and {{cssxref("margin-left")}}
- {{cssxref("margin")}} shorthand
- {{cssxref("margin-block-start")}}, {{cssxref("margin-block-end")}}, {{cssxref("margin-inline-start")}}, and {{cssxref("margin-inline-end")}}
- {{cssxref("margin-block")}} and {{cssxref("margin-inline")}} shorthands
- [CSS box model](/en-US/docs/Web/CSS/CSS_box_model) module
