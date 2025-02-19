# Uncommon HTML Bug: Incorrect Script Injection using innerHTML

This repository demonstrates a subtle bug related to using innerHTML to inject script tags into an HTML document.  The injected script may not execute reliably or might be blocked by the browser for security reasons.

The `bug.html` file showcases the problem, while `solution.html` provides the corrected approach.

## Bug Description
When using `innerHTML` to dynamically add content containing `<script>` tags, there's a chance the newly added script won't execute properly. This is because the browser's parsing and execution mechanisms may not immediately process the added script after modifying `innerHTML`.

## Solution
Instead of using `innerHTML` to inject scripts, create a new script element, set its attributes (like `src` or `textContent`), and then append it to the document using `appendChild`. This approach ensures the script is parsed and executed correctly by the browser.

## How to Reproduce
1. Clone the repository.
2. Open `bug.html` in your web browser.
3. Observe that the alert from the injected script may or may not appear.
4. Open `solution.html` and observe the expected alert behavior.