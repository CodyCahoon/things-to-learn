# things-to-learn

## Questions

1. What is shadow DOM and how is it used? [See Shadow DOM]
2. What are some benefits of shadow DOM? [See Shadow DOM]
3. What are the purpose of data attributes? [See Data Attributes]
4. What is the difference between bind, call and apply? [See Function Prototype]
5. What is the difference between virtual DOM and shadow DOM?
6. What is TCP/UDP?
7. How do you make a web component?
8. What are different CSS writing styles?
9. What are the pros and cons of utility vs component css frameworks?
10. What are closures?
11. What is currying?
12. What is requestAnimationFrame?

## Data Attributes

Enables additional information to be placed on an HTML element. Attributes can be accessed via JS using `el.dataset.size`. Attributes can be accessed via CSS using `content: attr(data-size)` or as selectors `article[data-size='large'] { width: 400px }`

## Function Prototype

| Function | Action                                                                              | Usage                                           |
| -------- | ----------------------------------------------------------------------------------- | ----------------------------------------------- |
| `bind`   | Returns a function with a provided context and any initial arguments passed through | `func.bind(obj, arg1, arg2) -> function`        |
| `call`   | Calls a function with a provided context and a spread list of arguments             | `func.call(obj, arg1, arg2) -> runs function`   |
| `apply`  | Calls a function with a provided context and arguments                              | `func.apply(obj, [arg1, arg2] -> runs function` |

## Shadow DOM

Shadow DOM is a DOM structure attached to an element (called the shadow host) to enapsulate its own DOM tree and CSS, hidden to the DOM. A shadow tree is not affected by outside CSS (unless including an external stylesheet as part of the shadow tree).

### Pros

1. Encapsulates styles, avoiding the need for higher specificity with selectors and keeping styles local
2. Encapsulates markup, creates separate DOM trees rather than one large global DOM

### Cons

1. Isolated styles means unable to use outside styles
2. Unable to parse shadow tree
