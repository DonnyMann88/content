---
title: Firefox 60 for developers
short-title: Firefox 60
slug: Mozilla/Firefox/Releases/60
page-type: firefox-release-notes
sidebar: firefox
---

This article provides information about the changes in Firefox 60 that will affect developers. Firefox 60 was released on May 9, 2018.

## Stylo comes to Firefox for Android in 60

[Firefox's new parallel CSS engine](https://hacks.mozilla.org/2017/08/inside-a-super-fast-css-engine-quantum-css-aka-stylo/) — also known as **Quantum CSS** or **Stylo** — which was [first enabled by default in Firefox 57 for desktop](/en-US/docs/Mozilla/Firefox/Releases/57#firefox_57_firefox_quantum), has now been enabled in Firefox for Android.

## Changes for web developers

### Developer tools

- In the CSS Pane rules view (see [Examine and edit CSS](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/examine_and_edit_css/index.html)), the keyboard shortcuts for precise value increments (increase/decrease by 0.1) have changed from `Alt` + `Up`/`Down` to `Ctrl` + `Up`/`Down` on Linux and Windows, to avoid clashes with default OS-level shortcuts (see [Firefox bug 1413314](https://bugzil.la/1413314)).
- Also in the CSS Pane rules view, [CSS variable names](/en-US/docs/Web/CSS/CSS_cascading_variables/Using_CSS_custom_properties) will now auto-complete ([Firefox bug 1422635](https://bugzil.la/1422635)). If you enter `var(` into a property value and then type a dash (`-`), any variables you have declared in your CSS will then appear in an autocomplete list.
- In [Responsive Design Mode](https://firefox-source-docs.mozilla.org/devtools-user/responsive_design_mode/index.html), a _Reload when…_ dropdown has been added to allow users to enable/disable automatic page reloads when touch simulation is toggled, or simulated user agent is changed. See [Controlling page reload behavior](https://firefox-source-docs.mozilla.org/devtools-user/responsive_design_mode/index.html#controlling-page-reload-behavior) for more details ([Firefox bug 1428816](https://bugzil.la/1428816)).
- The `view_source.tab` preference has been removed so you can no longer toggle [View Source](https://firefox-source-docs.mozilla.org/devtools-user/view_source/index.html) mode between appearing in a new tab or new window. Page sources will always appear in new tabs from now on ([Firefox bug 1418403](https://bugzil.la/1418403)).

### HTML

Pressing the Enter key in `designMode` and `contenteditable` now inserts `<div>` elements when the caret is in an inline element or text node which is a child of a block level editing host — instead of inserting `<br>` elements like it used to. If you want to use the old behavior on your app, you can do it with `document.execCommand()` ([Firefox bug 1430551](https://bugzil.la/1430551)).

### CSS

- The {{cssxref("align-content")}}, {{cssxref("align-items")}}, {{cssxref("align-self")}}, {{cssxref("justify-content")}}, and {{cssxref("place-content")}} property values have been updated as per the latest [CSS Box Alignment Module Level 3](https://drafts.csswg.org/css-align-3/) spec ([Firefox bug 1430817](https://bugzil.la/1430817)).
- The {{cssxref("paint-order")}} property has been implemented ([Firefox bug 1426146](https://bugzil.la/1426146)).

### SVG

_No changes._

### JavaScript

- ECMAScript 2015 modules have been enabled by default in ([Firefox bug 1438139](https://bugzil.la/1438139)). See [ES6 In Depth: Modules](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/) and [ES modules: A cartoon deep dive](https://hacks.mozilla.org/2018/03/es-modules-a-cartoon-deep-dive/) for more information, or consult MDN reference docs:
  - [`<script src="main.js" type="module">`](/en-US/docs/Web/HTML/Reference/Elements/script/type) and [`<script nomodule src="fallback.js">`](/en-US/docs/Web/HTML/Reference/Elements/script#nomodule)
  - [`import`](/en-US/docs/Web/JavaScript/Reference/Statements/import) and [`export`](/en-US/docs/Web/JavaScript/Reference/Statements/export) statements.

- The {{jsxref("Array.prototype.values()")}} method has been added again ([Firefox bug 1420101](https://bugzil.la/1420101)). Make sure your code doesn't have any custom implementation of this method.

### APIs

#### New APIs

- The [Web Authentication API](/en-US/docs/Web/API/Web_Authentication_API) has been enabled in ([Firefox bug 1432542](https://bugzil.la/1432542)).

#### DOM

- In the [Web Authentication API](/en-US/docs/Web/API/Web_Authentication_API), the `MakePublicKeyCredentialOptions` dictionary object has been renamed `PublicKeyCredentialCreationOptions`; this change has been made in Firefox ([Firefox bug 1436473](https://bugzil.la/1436473)).
- The `dom.workers.enabled` pref has been removed, meaning workers can no longer be disabled since ([Firefox bug 1434934](https://bugzil.la/1434934)).
- The {{domxref("Document.body","body")}} property is now implemented on the {{domxref("Document")}} interface, rather than the {{domxref("HTMLDocument")}} interface ([Firefox bug 1276438](https://bugzil.la/1276438)).
- {{domxref("PerformanceResourceTiming")}} is now available in workers ([Firefox bug 1425458](https://bugzil.la/1425458)).
- The {{domxref("PerformanceObserver.takeRecords()")}} method has been implemented ([Firefox bug 1436692](https://bugzil.la/1436692)).
- The {{domxref("KeyboardEvent.keyCode")}} attribute of punctuation key becomes non-zero even if the active keyboard layout doesn't produce ASCII characters. See [these notes for more detail](/en-US/docs/Web/API/KeyboardEvent/keyCode#printable_keys_in_standard_position). Please do **not** use `KeyboardEvent.keyCode` in new applications — use {{domxref("KeyboardEvent.key")}} or {{domxref("KeyboardEvent.code")}} instead.
- The {{domxref("Animation.updatePlaybackRate()")}} method has been implemented ([Firefox bug 1436659](https://bugzil.la/1436659)).
- New rules have been included for determining [keyCode values of punctuation keys](/en-US/docs/Web/API/KeyboardEvent/keyCode#printable_keys_in_standard_position) ([Firefox bug 1036008](https://bugzil.la/1036008)).
- The Gecko-only options object `storage` option of the {{domxref("IDBFactory.open()")}} method has been deprecated ([Firefox bug 1442560](https://bugzil.la/1442560)).
- [Promises](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) can now be used within [IndexedDB](/en-US/docs/Web/API/IndexedDB_API) code ([Firefox bug 1193394](https://bugzil.la/1193394)).

#### DOM events

_No changes._

#### Service workers

_No changes._

#### Media and WebRTC

- When recording or sharing media obtained using {{domxref("MediaDevices.getUserMedia", "getUserMedia()")}}, muting the camera by setting the corresponding track's {{domxref("MediaStreamTrack.enabled")}} property to `false` now turns off the camera's "in use" indicator light, to help the user more easily see that the camera is not in use ([Firefox bug 1299515](https://bugzil.la/1299515)). See [User privacy](/en-US/docs/Web/API/MediaDevices/getUserMedia#user_privacy) for more details. See also [this blog post](https://blog.mozilla.org/webrtc/better-privacy-on-camera-mute-in-firefox-60/).
- Removing a track from an {{domxref("RTCPeerConnection")}} using {{domxref("RTCPeerConnection.removeTrack", "removeTrack()")}} no longer removes the track's {{domxref("RTCRtpSender")}} from the peer connection's list of senders as reported by {{domxref("RTCPeerConnection.getSenders", "getSenders()")}} ([Firefox bug 1290949](https://bugzil.la/1290949)).
- The `RTCRtpContributingSource` and `RTCRtpSynchronizationSource` objects' timestamps were previously being reported based on values returned by {{jsxref("Date.getTime()")}}. In Firefox 60, these have been fixed to correctly use the [Performance Timing API](/en-US/docs/Web/API/Performance_API) instead ([Firefox bug 1433576](https://bugzil.la/1433576)).
- As per spec, the {{domxref("ConvolverNode.ConvolverNode","ConvolverNode()")}} constructor now throws a `NotSupportedError` {{domxref("DOMException")}} if the referenced {{domxref("AudioBuffer")}} does not have 1, 2, or 4 channels ([Firefox bug 1443228](https://bugzil.la/1443228)).
- The obsolete {{domxref("RTCPeerConnection")}} event handler {{domxref("RTCPeerConnection.removestream_event", "RTCPeerConnection.onremovestream")}} has been removed; by now you should be using {{domxref("MediaStream/removetrack_event", "removetrack")}} events instead ([Firefox bug 1442385](https://bugzil.la/1442385)).
- The primary name for {{domxref("RTCDataChannel")}} is now in fact `RTCDataChannel`, instead of being an alias for `DataChannel`. The name `DataChannel` is no longer supported ([Firefox bug 1173851](https://bugzil.la/1173851)).

#### Canvas and WebGL

- If the `privacy.resistFingerprinting` preference is set to `true`, the {{domxref("WEBGL_debug_renderer_info")}} WebGL extension will be disabled from now on ([Firefox bug 1337157](https://bugzil.la/1337157)).

### CSSOM

_No changes._

### HTTP

- `SameSite` cookies are now supported ([Firefox bug 795346](https://bugzil.la/795346)). See {{HTTPHeader("Set-Cookie")}} for more information.

### Security

The {{httpheader("X-Content-Type-Options")}} header, when set to `no-sniff`, now follows the specification for JavaScript MIME types. In particular, `text/json` and `application/json` are no longer valid values ([Firefox bug 1431095](https://bugzil.la/1431095)).

### Plugins

_No changes._

### Other

Fetches that include credentials can now share connections with fetches that don't include credentials. For example, if the same origin requests some web fonts as well as some credentialed user data from the same CDN, both could share a connection, potentially leading to a quicker turnaround ([Firefox bug 1363284](https://bugzil.la/1363284)).

## Removals from the web platform

### HTML

_No changes._

### CSS

- The proprietary {{cssxref("-moz-user-input")}} property's `enabled` and `disabled` values are no longer available ([Firefox bug 1405087](https://bugzil.la/1405087)).
- The proprietary `-moz-border-top-colors`, `-moz-border-right-colors`, `-moz-border-bottom-colors`, and `-moz-border-left-colors` properties have been removed from the platform completely ([Firefox bug 1429723](https://bugzil.la/1429723)).

### JavaScript

The non-standard [expression closure](/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features#statements_2) syntax has been removed ([Firefox bug 1426519](https://bugzil.la/1426519)).

### APIs

_No changes._

### SVG

_No changes._

### Other

_No changes._

## Changes for add-on and Mozilla developers

### WebExtensions

Theme API:

- headerURL is now optional
- When creating a browser [theme](/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json/theme), any {{cssxref("text-shadow")}} applied to the header text is removed if no `headerURL` is specified (see [Firefox bug 1404688](https://bugzil.la/1404688)).
- New properties are supported:
  - **tab_line**
  - **tab_selected**
  - **popup**
  - **popup_border**
  - **popup_text**
  - **tab_loading**
  - **icons**
  - **icons_attention**
  - **frame_inactive**
  - **button_background_active**
  - **button_background_hover**
