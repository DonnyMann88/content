---
title: HTML enterkeyhint global attribute
short-title: enterkeyhint
slug: Web/HTML/Reference/Global_attributes/enterkeyhint
page-type: html-attribute
browser-compat: html.global_attributes.enterkeyhint
sidebar: htmlsidebar
---

The **`enterkeyhint`** [global attribute](/en-US/docs/Web/HTML/Reference/Global_attributes)
is an [enumerated](/en-US/docs/Glossary/Enumerated) attribute defining what action label (or icon) to present for the enter key on virtual keyboards.

{{InteractiveExample("HTML Demo: enterkeyhint", "tabbed-shorter")}}

```html interactive-example
<input enterkeyhint="go" />

<p contenteditable enterkeyhint="go">https://example.org</p>
```

## Description

[Form controls](/en-US/docs/Learn_web_development/Extensions/Forms) (such as [`<textarea>`](/en-US/docs/Web/HTML/Reference/Elements/textarea)
or [`<input>`](/en-US/docs/Web/HTML/Reference/Elements/input) elements) or elements using
[`contenteditable`](/en-US/docs/Web/HTML/Reference/Global_attributes/contenteditable) can specify an
[`inputmode`](/en-US/docs/Web/HTML/Reference/Global_attributes/inputmode) attribute to control what kind of virtual keyboard
will be used. To further improve the user's experience, the enter key can be customized specifically by providing an `enterkeyhint`
attribute indicating how the enter key should be labeled (or which icon should be shown). The enter key usually
represents what the user should do next; typical actions are: sending text, inserting a new line, or searching.

If no `enterkeyhint` attribute is provided, the user agent might use contextual information from the
[`inputmode`](/en-US/docs/Web/HTML/Reference/Global_attributes/inputmode),
[`type`](/en-US/docs/Web/HTML/Reference/Elements/input#input_types),
or [`pattern`](/en-US/docs/Web/HTML/Reference/Elements/input#pattern)
attributes to display a suitable enter key label (or icon).

## Value

The `enterkeyhint` attribute is an [enumerated](/en-US/docs/Glossary/Enumerated) attribute and only accepts the following values:

<table class="no-markdown">
  <thead>
    <tr>
      <th>Value</th>
      <th>Description</th>
      <th>Example label (depends on user agent and user language)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>enterkeyhint="enter"</code></td>
      <td>Typically inserting a new line.</td>
      <td><kbd>return</kbd>, <kbd>↵</kbd></td>
    </tr>
    <tr>
      <td><code>enterkeyhint="done"</code></td>
      <td>Typically meaning there is nothing more to input and the input method editor (IME) will be closed.</td>
      <td><kbd>done</kbd>, <kbd>✅</kbd></td>
    </tr>
    <tr>
      <td><code>enterkeyhint="go"</code></td>
      <td>Typically meaning to take the user to the target of the text they typed.</td>
      <td><kbd>go</kbd>, <kbd>🡢</kbd></td>
    </tr>
    <tr>
      <td><code>enterkeyhint="next"</code></td>
      <td>Typically taking the user to the next field that will accept text.</td>
      <td><kbd>next</kbd>, <kbd>⇥</kbd></td>
    </tr>
    <tr>
      <td><code>enterkeyhint="previous"</code></td>
      <td>Typically taking the user to the previous field that will accept text.</td>
      <td><kbd>return</kbd>, <kbd>⇤</kbd></td>
    </tr>
    <tr>
      <td><code>enterkeyhint="search"</code></td>
      <td>Typically taking the user to the results of searching for the text they have typed.</td>
      <td><kbd>search</kbd>, <kbd>🔍</kbd></td>
    </tr>
    <tr>
      <td><code>enterkeyhint="send"</code></td>
      <td>Typically delivering the text to its target.</td>
      <td><kbd>send</kbd></td>
    </tr>
  </tbody>
</table>

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [`HTMLElement.enterKeyHint`](/en-US/docs/Web/API/HTMLElement/enterKeyHint) property reflecting this attribute
- [`inputmode`](/en-US/docs/Web/HTML/Reference/Global_attributes/inputmode) global attribute
- [`contenteditable`](/en-US/docs/Web/HTML/Reference/Global_attributes/contenteditable) global attribute
- [`type`](/en-US/docs/Web/HTML/Reference/Elements/input#input_types) and
  [`pattern`](/en-US/docs/Web/HTML/Reference/Elements/input#pattern) attributes on
  [`<input>`](/en-US/docs/Web/HTML/Reference/Elements/input) elements
