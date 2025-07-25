---
title: "<abbr>: The Abbreviation element"
slug: Web/HTML/Reference/Elements/abbr
page-type: html-element
browser-compat: html.elements.abbr
sidebar: htmlsidebar
---

The **`<abbr>`** [HTML](/en-US/docs/Web/HTML) element represents an abbreviation or acronym.

When including an abbreviation or acronym, provide a full expansion of the term in plain text on first use, along with the `<abbr>` to mark up the abbreviation. This informs the user what the abbreviation or acronym means.

The optional [`title`](/en-US/docs/Web/HTML/Reference/Global_attributes/title) attribute can provide an expansion for the abbreviation or acronym when a full expansion is not present. This provides a hint to user agents on how to announce/display the content while informing all users what the abbreviation means. If present, `title` must contain this full description and nothing else.

{{InteractiveExample("HTML Demo: &lt;abbr&gt;", "tabbed-shorter")}}

```html interactive-example
<p>
  You can use <abbr>CSS</abbr> (Cascading Style Sheets) to style your
  <abbr>HTML</abbr> (HyperText Markup Language). Using style sheets, you can
  keep your <abbr>CSS</abbr> presentation layer and <abbr>HTML</abbr> content
  layer separate. This is called "separation of concerns."
</p>
```

```css interactive-example
abbr {
  font-style: italic;
  color: chocolate;
}
```

## Attributes

This element only supports the [global attributes](/en-US/docs/Web/HTML/Reference/Global_attributes). The [`title`](/en-US/docs/Web/HTML/Reference/Global_attributes/title) attribute has a specific semantic meaning when used with the `<abbr>` element; it _must_ contain a full human-readable description or expansion of the abbreviation. This text is often presented by browsers as a tooltip when the mouse cursor is hovered over the element.

Each `<abbr>` element you use is independent of all others; providing a `title` for one does not automatically attach the same expansion text to others with the same content text.

## Usage notes

### Typical use cases

It's certainly not required that all abbreviations be marked up using `<abbr>`. There are, though, a few cases where it's helpful to do so:

- When an abbreviation is used and you want to provide an expansion or definition outside the flow of the document's content, use `<abbr>` with an appropriate [`title`](/en-US/docs/Web/HTML/Reference/Global_attributes/title).
- To define an abbreviation which may be unfamiliar to the reader, present the term using `<abbr>` and inline text providing the definition. Include a `title` attribute only when the inline expansion or definition is not available.
- When an abbreviation's presence in the text needs to be semantically noted, the `<abbr>` element is useful. This can be used, in turn, for styling or scripting purposes.
- You can use `<abbr>` in concert with {{HTMLElement("dfn")}} to establish definitions for terms which are abbreviations or acronyms. See the example [Defining an abbreviation](#defining_an_abbreviation) below.

### Grammar considerations

In languages with [grammatical number](https://en.wikipedia.org/wiki/Grammatical_number) (that is, languages where the number of items affects the grammar of a sentence), use the same grammatical number in your `title` attribute as inside your `<abbr>` element. This is especially important in languages with more than two numbers, such as Arabic, but is also relevant in English.

## Default styling

The purpose of this element is purely for the convenience of the author and all browsers display it inline ({{cssxref("display", "display: inline")}}) by default, though its default styling varies from one browser to another:

Some browsers add a dotted underline to the content of the element. Others add a dotted underline while converting the contents to small caps. Others may not style it differently than a {{HTMLElement("span")}} element. To control this styling, use {{cssxref('text-decoration')}} and {{cssxref('font-variant')}}.

## Accessibility

Spelling out the acronym or abbreviation in full the first time it is used on a page is beneficial for helping people understand it, especially if the content is technical or industry jargon.

Only include a `title` if expanding the abbreviation or acronym in the text is not possible. Having a difference between the announced word or phrase and what is displayed on the screen, especially if it's technical jargon the reader may not be familiar with, can be jarring.

```html
<p>
  JavaScript Object Notation (<abbr>JSON</abbr>) is a lightweight
  data-interchange format.
</p>
```

{{EmbedLiveSample("Accessibility")}}

This is especially helpful for people who are unfamiliar with the terminology or concepts discussed in the content, people who are new to the language, and people with cognitive concerns.

## Examples

### Marking up an abbreviation semantically

To mark up an abbreviation without providing an expansion or description, use `<abbr>` without any attributes, as seen in this example.

#### HTML

```html
<p>Using <abbr>HTML</abbr> is fun and easy!</p>
```

#### Result

{{EmbedLiveSample("Marking_up_an_abbreviation_semantically")}}

### Styling abbreviations

You can use CSS to set a custom style to be used for abbreviations, as seen in this basic example.

#### HTML

```html
<p>Using <abbr>CSS</abbr>, you can style your abbreviations!</p>
```

#### CSS

```css
abbr {
  font-variant: all-small-caps;
}
```

#### Result

{{EmbedLiveSample("Styling_abbreviations")}}

### Providing an expansion

Adding a [`title`](/en-US/docs/Web/HTML/Reference/Global_attributes/title) attribute lets you provide an expansion or definition for the abbreviation or acronym.

#### HTML

```html
<p>Ashok's joke made me <abbr title="Laugh Out Loud">LOL</abbr> big time.</p>
```

#### Result

{{EmbedLiveSample("Providing_an_expansion")}}

### Defining an abbreviation

You can use `<abbr>` in tandem with {{HTMLElement("dfn")}} to more formally define an abbreviation, as shown here.

#### HTML

```html
<p>
  <dfn id="html"><abbr title="HyperText Markup Language">HTML</abbr> </dfn> is a
  markup language used to create the semantics and structure of a web page.
</p>

<p>
  A <dfn id="spec">Specification</dfn> (<abbr>spec</abbr>) is a document that
  outlines in detail how a technology or API is intended to function and how it
  is accessed.
</p>
```

#### Result

{{EmbedLiveSample("Defining_an_abbreviation", 600, 120)}}

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
        >,
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content"
          >phrasing content</a
        >, palpable content
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted content</th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content"
          >Phrasing content</a
        >
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
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content"
          >phrasing content</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">Implicit ARIA role</th>
      <td>
        <a href="https://w3c.github.io/html-aria/#dfn-no-corresponding-role"
          >No corresponding role</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted ARIA roles</th>
      <td>Any</td>
    </tr>
    <tr>
      <th scope="row">DOM Interface</th>
      <td>{{domxref("HTMLElement")}}</td>
    </tr>
  </tbody>
</table>

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Using the `<abbr>` element](/en-US/docs/Learn_web_development/Core/Structuring_content/Advanced_text_features#abbreviations)
