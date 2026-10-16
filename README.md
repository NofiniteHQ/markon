<p align="center">
  <a href="https://github.com/NofiniteHQ/markon">
    <img src="./markon.png" alt="Markon logo" width="100%" />
  </a>
</p>
<p align="center">
  <a href="https://nofinite.com">
   <img alt="Static Badge" src="https://img.shields.io/badge/Nofinite-%23000133?style=for-the-badge&label=FROM&labelColor=slategray">
  </a>
  
  <a href="https://github.com/NofiniteHQ/markon/blob/main/LICENSE">
   <img alt="GitHub License" src="https://img.shields.io/github/license/nofinitehq/markon?style=for-the-badge&labelColor=slategray&color=%23000133">
  </a>
  
  <a href="https://www.npmjs.com/package/@nofinite/markon">
   <img alt="NPM Version" src="https://img.shields.io/npm/v/%40nofinite%2Fmarkon?style=for-the-badge&logo=npm&logoColor=white&labelColor=slategray&color=%23000133">
  </a>
</p>

> Markon has evolved. Explore [Markon v2](https://opensource.nofinite.com/markon).

## The Story Behind Markon

Markon started with a simple idea: content should be structured as data, while the UI should decide how it is presented.

We created Markon to make Nofinite's content JSON-based, allowing interfaces to render and present it consistently without having to write custom markup for every piece of content.

We used this approach for policies, About pages, documentation, and other content-heavy pages across the Nofinite ecosystem. Over time, Markon became part of how we managed and presented content across our products.

## Markon v2

As our needs evolved, so did Markon.

Markon v2 builds on the original idea with a more capable approach to parsing, compiling, and rendering content. Its implementation has evolved significantly while retaining the goal of making content easier to work with across applications.

Development of Markon v2 now lives in the [Nofinite Stack repository](https://github.com/NofiniteHQ/stack/tree/main/packages/markon).

Maintaining an existing v1 project? Continue with the documentation below.

This repository preserves the original Markon v1 implementation and its history. It is no longer actively developed.

---

## Introduction (Markon v1)
Markon is a lightweight JavaScript library designed for effortless content formatting in React and HTML applications. Simplify text styling tasks like bolding, adding links, lists, and line breaks with Markon, allowing developers to focus on content creation without dealing with complex formatting.

## Markon Syntax
Markon employs a simple and intuitive syntax to enhance text formatting:

- **Bold: `#b[Text]#`**  
  Surround your text with `#b[` and `]#` to make it bold.
- **Underline: `#u[Text]#`**
  Surround your text with `#u[` and `]#` to make it underline.
- **Emphasize: `#e[Text]#`**
  Surround your text with `#e[` and `]#` to make it emphasize.
- **List: `#list[Item1, Item2]#`**  
  Create a list by enclosing items in `#list[` and `]#`.
- **Link: `#link[Text, URL]#`**  
  Insert a link with text and URL specified within `#link[` and `]#`.
- **Line Break: `#br#`**   
  Introduce a line break with `#br#`.

Example:  
- Use Markon in Text (String):  
`"Hello #b[Markon]#"`
- Output:  
Hello **Markon**

## Installation

**Markon offers two convenient options for integration: a component (`ReactMarkon`) tailored for React, Next.js, etc.-based applications, and a JavaScript function (`JSMarkon`) designed for HTML-based applications.**

  
### ReactMarkon (Component):  

Installation:  
```bash
npm install @nofinite/markon@1
```   

Usage in JSX:  
```jsx
import { ReactMarkon } from "@nofinite/markon";

const Blog = () => {
    // Value must be a string
    const value = "#b[Markon]#, #br#, #link[Markon, https://github.com/NofiniteHQ/markon]#, #list[Item 1, Item 2]#";

    // Component returns formatted content
    return <ReactMarkon content={value} />;
};
```

### JSMarkon (Function):  

Installation:  
   
Download the file: [JSMarkon.min.js](https://raw.githubusercontent.com/NofiniteHQ/markon/main/dist/JSMarkon.min.js)   

> Security note: JSMarkon output is rendered using innerHTML. Only use trusted content; sanitize untrusted input before rendering to prevent cross-site scripting (XSS).

Usage in HTML:  
```HTML
<!doctype html>
<html>
  <head></head>
  <body>
    <div id="showContent"></div>

    <script src="./JSMarkon.min.js"></script>
    <script>
      // Value must be a string
      const value = "#b[Markon]#, #br# #link[Markon, https://github.com/NofiniteHQ/markon]#, #list[Item 1, Item 2]#";

      // Function returns formatted content
      const result = JSMarkon(value);

      // Render result using innerHTML
      document.getElementById("showContent").innerHTML = result;
    </script>
  </body>
</html>
```

## Contributors
[Markon Contributors](https://github.com/NofiniteHQ/markon/graphs/contributors)

## License
Markon is [MIT licensed](https://github.com/NofiniteHQ/markon/blob/main/LICENSE)
