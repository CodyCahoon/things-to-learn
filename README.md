# things-to-learn

## Questions

1. What is shadow DOM and how is it used? [See DOM]
2. What are some benefits of shadow DOM? [See DOM]
3. What are the purpose of data attributes? [See Data Attributes]
4. What is the difference between bind, call and apply? [See Function Prototype]
5. What is the difference between virtual DOM and shadow DOM? [See DOM]
6. What is TCP/UDP?
7. How do you make a web component? [See Web Components]
8. What are different CSS writing styles?
9. What are the pros and cons of utility vs component css frameworks?
10. What are closures?
11. What is currying?
12. What is requestAnimationFrame?
13. Why should I use semantic HTML?
14. When should I use `px`, `em`, `rem`, `%` in CSS?
15. What are `min`, `max`, and `clamp` in CSS?
16. What is ACID?
17. What is a web worker?
18. What is a service worker?
19. How does a web socket work?
20. What are the features of ES5, ES6, ES7, etc.?

## Data Attributes

Enables additional information to be placed on an HTML element. Attributes can be accessed via JS using `el.dataset.size`. Attributes can be accessed via CSS using `content: attr(data-size)` or as selectors `article[data-size='large'] { width: 400px }`

## Document Object Model (DOM)

### Shadow

Shadow DOM is a DOM structure attached to an element (called the shadow host) to enapsulate its own DOM tree and CSS, hidden to the DOM. A shadow tree is not affected by outside CSS (unless including an external stylesheet as part of the shadow tree).

| Pros                                                                   | Cons                           |
| ---------------------------------------------------------------------- | ------------------------------ |
| Avoids higher specificity for styling selectors and keeps styles local | Unable to access global styles |
| Creates separate DOM trees rather than one large global DOM            | Unable to parse shadow tree    |

### Virtual

JS representation of a DOM tree, used to avoid directly altering the DOM when unnecessary. It is used heavily with Vue and React frameworks to avoid re-rendering the HTML, to avoid performance hits. Virtual DOM attempts to render any necessary changes at once.

## Function Prototype

| Function | Action                                                                              | Usage                                           |
| -------- | ----------------------------------------------------------------------------------- | ----------------------------------------------- |
| `bind`   | Returns a function with a provided context and any initial arguments passed through | `func.bind(obj, arg1, arg2) -> function`        |
| `call`   | Calls a function with a provided context and a spread list of arguments             | `func.call(obj, arg1, arg2) -> runs function`   |
| `apply`  | Calls a function with a provided context and arguments                              | `func.apply(obj, [arg1, arg2] -> runs function` |

## Web Components

Web components use custom elements, shadow DOM, templates and slots to render customer components across browsers.

### Custom Elements

```js
class NewWebComponent extends HTMLElement {...}
window.customElements.define('custom-tag', NewWebComponent);
```

```html
<custom-tag input1="hello" input2="test"></custom-tag>
```

| Event                                      | Purpose                                                                                       |
| ------------------------------------------ | --------------------------------------------------------------------------------------------- |
| `constructor`                              | Creates the web component, used to create shadow DOM, listeners and component state           |
| `connectedCallback`                        | When the element is added to the DOM, used to set attributes, setup code, or render templates |
| `disconnectedCallback`                     | When the element is removed from the DOM, used to clean up listeners and avoid memory leaks   |
| `attributeChangedCallback(name, new, old)` | When a single attribute on the class is changed                                               |
| `static get observedAttributes()`          | Returns a list of which properties to watch for changes                                       |
