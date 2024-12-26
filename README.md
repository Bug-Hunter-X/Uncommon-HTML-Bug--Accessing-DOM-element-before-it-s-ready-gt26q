# Uncommon HTML Bug: Accessing DOM Element Before it's Ready
This repository demonstrates an uncommon HTML bug related to accessing DOM elements before they are fully loaded into the DOM. This often leads to a `ReferenceError: Cannot read properties of null (reading 'innerHTML')` error.

## The Bug
The bug lies in the order of execution. The script attempts to manipulate a DOM element ('myDiv') before the HTML parser has finished loading this element. The script runs before the element is available in the DOM, so `document.getElementById('myDiv')` returns null causing the error. 

## Solution
The solution is to ensure that the script that accesses the DOM element runs only after the DOM is completely loaded. This is typically achieved by placing the script at the end of the `<body>` or by using the `DOMContentLoaded` event listener.