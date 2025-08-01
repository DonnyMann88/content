---
title: "Node: insertBefore() method"
short-title: insertBefore()
slug: Web/API/Node/insertBefore
page-type: web-api-instance-method
browser-compat: api.Node.insertBefore
---

{{APIRef("DOM")}}

The **`insertBefore()`** method of the {{domxref("Node")}} interface
inserts a node before a _reference node_ as a child of a specified _parent node_.

If the given node already exists in the document,
`insertBefore()` moves it from its current position to the new position.
(That is, it will automatically be removed from its existing parent
before appending it to the specified new parent.)

This means that a node cannot be in two locations of the document simultaneously.

> [!NOTE]
> The {{domxref("Node.cloneNode()")}} can be used to make a copy
> of the node before appending it under the new parent. Note that the copies made with
> `cloneNode()` will not be automatically kept in sync.

If the given child is a {{domxref("DocumentFragment")}}, the entire contents of the
`DocumentFragment` are moved into the child list of the specified parent
node.

## Syntax

```js-nolint
insertBefore(newNode, referenceNode)
```

### Parameters

- `newNode`
  - : The node to be inserted.
- `referenceNode`
  - : The node before which `newNode` is inserted. If this is
    `null`, then `newNode` is inserted at the end of
    node's child nodes.
    > [!NOTE]
    > `referenceNode` is **not** an optional parameter.
    > You must explicitly pass a {{domxref("Node")}} or `null`.
    > Failing to provide it or passing invalid values may [behave](https://crbug.com/419780) [differently](https://bugzil.la/119489) in different browser versions.

### Return value

Returns the added child (unless `newNode` is a {{domxref("DocumentFragment")}},
in which case the empty {{domxref("DocumentFragment")}} is returned).

### Exceptions

Pre-insert validity

## Example

### Example 1

```html
<div id="parentElement">
  <span id="childElement">foo bar</span>
</div>
```

```js
// Create the new node to insert
const newNode = document.createElement("span");

// Get a reference to the parent node
const parentDiv = document.getElementById("childElement").parentNode;

// Begin test case [ 1 ] : Existing childElement (all works correctly)
let sp2 = document.getElementById("childElement");
parentDiv.insertBefore(newNode, sp2);
// End test case [ 1 ]

// Begin test case [ 2 ] : childElement is of Type undefined
sp2 = undefined; // Non-existent node of id "childElement"
parentDiv.insertBefore(newNode, sp2); // Implicit dynamic cast to type Node
// End test case [ 2 ]

// Begin test case [ 3 ] : childElement is of Type "undefined" (string)
sp2 = "undefined"; // Non-existent node of id "childElement"
parentDiv.insertBefore(newNode, sp2); // Generates "Type Error: Invalid Argument"
// End test case [ 3 ]
```

### Example 2

```html
<div id="parentElement">
  <span id="childElement">foo bar</span>
</div>
```

```js
// Create a new, plain <span> element
const sp1 = document.createElement("span");

// Get the reference element
const sp2 = document.getElementById("childElement");
// Get the parent element
const parentDiv = sp2.parentNode;

// Insert the new element into before sp2
parentDiv.insertBefore(sp1, sp2);
```

> [!NOTE]
> There is no `insertAfter()` method.
> It can be emulated by combining the `insertBefore` method
> with {{domxref("Node.nextSibling")}}.
>
> In the previous example, `sp1` could be inserted after `sp2` using:
>
> ```js
> parentDiv.insertBefore(sp1, sp2.nextSibling);
> ```
>
> If `sp2` does not have a next sibling, then it must be the last child —
> `sp2.nextSibling` returns `null`, and `sp1` is inserted
> at the end of the child node list (immediately after `sp2`).

### Example 3

Insert an element before the first child element, using the
{{domxref("Node/firstChild", "firstChild")}} property.

```js
// Get the parent element
const parentElement = document.getElementById("parentElement");
// Get the parent's first child
const theFirstChild = parentElement.firstChild;

// Create a new element
const newElement = document.createElement("div");

// Insert the new element before the first child
parentElement.insertBefore(newElement, theFirstChild);
```

When the element does not have a first child, then `firstChild` is
`null`. The element is still appended to the parent, after the last child.

Since the parent element did not have a first child, it did not have a last child,
either. Consequently, the newly inserted element is the _only_ element.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("Node.removeChild()")}}
- {{domxref("Node.replaceChild()")}}
- {{domxref("Node.appendChild()")}}
- {{domxref("Node.hasChildNodes()")}}
- {{domxref("Element.insertAdjacentElement()")}}
- {{domxref("Element.prepend()")}}
- {{domxref("Element.before()")}}
- {{domxref("Element.after()")}}
