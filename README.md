#ngClipBoard

An angular directive to help you copy text to clipboard. Without Flash or anyother dependencies

------

#Usage
Import `ngClipBoard.js`:
```
<srcipt type="text/javascript" src="ngClipBoard.js">
```

Inject `clipBoard` to your angular project:
```
var app = angular.module('appName', [
        //...
        'clipBoard'
        //...
    ])
```
------
##1、Copy or cut text from other element

First, add a `clip-board` attribute as an angular directive in your trigger element.

Then you can set copying or cutting by adding a `clip-board-target` attribute in your trigger element.

Additionally, you can define a `clip-board-action` attribute to specify if you want to either copy or cut content.

```
<!-- Target -->
<input id="target" value="Text you wanna copy or cut">

<!-- Trigger -->
<button clip-board clip-board-target="#target" clip-board-action="copy/cut">
</button>
```
------
##2、Copy text from attribute
First, add a `clip-board` attribute as an angular directive in your trigger element.

And then just include a `clip-board-text` attribute in your trigger element.
```
<!-- Trigger -->
<button clip-board clip-board-text="Text you wanna copy">
    Copy to clipboard
</button>
```
------

##Architecture

This is a encapsulation of [zenorocha/clipboard.js][1].

The working principle is:
 1. Add a hidden `textarea` into the DOM.;
 2. Write the content that you want to copy into the `textarea`;
 3. Use `textarea.select()` to select the content;
 4. Call `document.execCommand()` to copy it;
 5. Remove `textarea`.

-------

##License
The MIT License
  [1]: https://github.com/zenorocha/clipboard.js