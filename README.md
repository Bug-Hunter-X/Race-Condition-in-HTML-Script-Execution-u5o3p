# Uncommon HTML Bug: Race Condition in Element Modification

This repository demonstrates a subtle race condition in HTML that can occur when JavaScript attempts to modify a DOM element before the element has finished loading.

## The Bug

The `bug.html` file contains a script that tries to modify the `innerHTML` of a div element (`myDiv`) immediately after the div is defined. In some browsers or under certain conditions, this can lead to the modification being ignored or to unexpected behavior.

## The Solution

The `solution.html` file demonstrates a more robust approach. It uses the `DOMContentLoaded` event listener to ensure that the script executes only after the DOM is fully parsed and ready for modifications.  This prevents the race condition.

## How to Reproduce

1. Clone this repository.
2. Open `bug.html` in your web browser.  You might see unexpected results.
3. Open `solution.html` in your web browser. You should see 'Hello World!' displayed correctly. 

## Further Notes

This bug highlights the importance of understanding the timing of script execution in web pages and the necessity of employing appropriate techniques, such as event listeners, to ensure that DOM manipulations are performed only when the DOM is fully loaded.