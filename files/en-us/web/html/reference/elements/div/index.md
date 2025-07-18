---
title: "<div>: The Content Division element"
slug: Web/HTML/Reference/Elements/div
page-type: html-element
browser-compat: html.elements.div
sidebar: htmlsidebar
---

The **`<div>`** [HTML](/en-US/docs/Web/HTML) element is the generic container for flow content. It has no effect on the content or layout until styled in some way using {{glossary("CSS")}} (e.g., styling is directly applied to it, or some kind of layout model like [Flexbox](/en-US/docs/Web/CSS/CSS_flexible_box_layout) is applied to its parent element).

{{InteractiveExample("HTML Demo: &lt;div&gt;", "tabbed-standard")}}

```html interactive-example
<div class="warning">
  <img
    src="/shared-assets/images/examples/leopard.jpg"
    alt="An intimidating leopard." />
  <p>Beware of the leopard</p>
</div>
```

```css interactive-example
.warning {
  border: 10px ridge #f00;
  background-color: #ff0;
  padding: 0.5rem;
  display: flex;
  flex-direction: column;
}

.warning img {
  width: 100%;
}

.warning p {
  font: small-caps bold 1.2rem sans-serif;
  text-align: center;
}
```

As a "pure" container, the `<div>` element does not inherently represent anything. Instead, it's used to group content so it can be easily styled using the [`class`](/en-US/docs/Web/HTML/Reference/Global_attributes/class) or [`id`](/en-US/docs/Web/HTML/Reference/Global_attributes/id) attributes, marking a section of a document as being written in a different language (using the [`lang`](/en-US/docs/Web/HTML/Reference/Global_attributes/lang) attribute), and so on.

## Attributes

This element includes the [global attributes](/en-US/docs/Web/HTML/Reference/Global_attributes).

> [!NOTE]
> The `align` attribute is obsolete; do not use it anymore. Instead, you should use CSS properties or techniques such as [CSS Grid](/en-US/docs/Web/CSS/CSS_grid_layout) or [CSS Flexbox](/en-US/docs/Learn_web_development/Core/CSS_layout/Flexbox) to align and position `<div>` elements on the page.

## Usage notes

- The `<div>` element should be used only when no other semantic element (such as {{HTMLElement("article")}} or {{HTMLElement("nav")}}) is appropriate.

## Accessibility

The `<div>` element has [an implicit role of `generic`](https://w3c.github.io/aria/#generic), and not none. This may affect certain ARIA combination declarations that expect a direct descendant element with a certain role to function properly.

## Examples

### A basic example

```html
<div>
  <p>
    Any kind of content here. Such as &lt;p&gt;, &lt;table&gt;. You name it!
  </p>
</div>
```

#### Result

{{EmbedLiveSample("A_basic_example", 650, 60)}}

### A styled example

This example creates a shadowed box by applying a style to the `<div>` using CSS. Note the use of the [`class`](/en-US/docs/Web/HTML/Reference/Global_attributes/class) attribute on the `<div>` to apply the style named `"shadowbox"` to the element.

#### HTML

```html
<div class="shadowbox">
  <p>Here's a very interesting note displayed in a lovely shadowed box.</p>
</div>
```

#### CSS

```css
.shadowbox {
  width: 15em;
  border: 1px solid #333;
  box-shadow: 8px 8px 5px #444;
  padding: 8px 12px;
  background-image: linear-gradient(180deg, #fff, #ddd 40%, #ccc);
}
```

#### Result

{{EmbedLiveSample("A_styled_example", 650, 120)}}

## Technical summary

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories"
          >Content categories</a
        >
      </th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#flow_content"
          >Flow content</a
        >, <a href="/en-US/docs/Web/HTML/Guides/Content_categories#palpable_content">palpable content</a>.
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted content</th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#flow_content"
          >Flow content</a
        >.<br />Or (in {{glossary("WHATWG")}} HTML): If the parent is a
        {{HTMLElement("dl")}} element: one or more
        {{HTMLElement("dt")}} elements followed by one or more
        {{HTMLElement("dd")}} elements, optionally intermixed with
        {{HTMLElement("script")}} and
        {{HTMLElement("template")}} elements.
      </td>
    </tr>
    <tr>
      <th scope="row">Tag omission</th>
      <td>None, both the starting and ending tag are mandatory.</td>
    </tr>
    <tr>
      <th scope="row">Permitted parents</th>
      <td>
        Any element that accepts
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#flow_content"
          >flow content</a
        >.<br />Or (in {{glossary("WHATWG")}} HTML):
        {{HTMLElement("dl")}} element.
      </td>
    </tr>
    <tr>
      <th scope="row">Implicit ARIA role</th>
      <td>
        <code
          ><a href="/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/generic_role"
            >generic</a
          ></code
        >
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted ARIA roles</th>
      <td>Any</td>
    </tr>
    <tr>
      <th scope="row">DOM interface</th>
      <td>{{domxref("HTMLDivElement")}}</td>
    </tr>
  </tbody>
</table>

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- Semantic sectioning elements: {{HTMLElement("section")}}, {{HTMLElement("article")}}, {{HTMLElement("nav")}}, {{HTMLElement("header")}}, {{HTMLElement("footer")}}
- {{HTMLElement("span")}} element for styling of phrasing content
