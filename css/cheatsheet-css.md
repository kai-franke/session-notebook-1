## Linking Stylesheets

```html
<head>
	...
	<link rel="stylesheet" href="styles.css" />
</head>
```

## CSS syntax
| Part           | Description                                                                                       |
| -------------- | ------------------------------------------------------------------------------------------------- |
| Selector       | Addresses the element(s) to style                                                                 |
| Declaration    | Defines what to change and contains pairs of `property` and `property value`                      |
| Property       | The name of the property to change                                                                |
| Property Value | The value assigned to the property, e.g for the property `color` we use the property value `blue` |

## CSS Properties
| Property           | Effect                                         |
| ------------------ | ---------------------------------------------- |
| `color`            | Color of an element´s text                     |
| `font-size`        | Defines the size of a font                     |
| `text-align`       | Defines the alignment of text                  |
| `background-color` | Background color of an element                 |
| `border`           | Defines the border of an element.              |
| `padding`          | Defines the padding of an element.             |
| `margin`           | Defines the margin of an element.              |
| `width`            | This property defines the width of an element. |
| `box-sizing`            | The property changes the way how the width and height of an element is calculated.The default value is content-box |
| `display`            | grid/flex |
| `font-family`            | grid/flex |
| `font-size`            | grid/flex |
| `font-weight`            | grid/flex |

## Box Model

All elements of a website are wrapped in a **box model**. It's a way to define the size and position
of an element. There are four different parts: `content`, `padding`, `border` and `margin`.

| box model part | Function                                                 |
| -------------- | -------------------------------------------------------- |
| `content`      | The actual content of the element.                       |
| `padding`      | Space between the content and the border of the element. |
| `border`       | The border of the element.                               |
| `margin`       | The space around the border and other elements.          |

The property `box-sizing` changes the way how the `width` and `height` of an element is calculated.
The default value is `content-box`. The values of `width` and `height` set the size of the "content
box". With the value `border-box`, the size of the "border box" is set instead.

```css
* {
	box-sizing: border-box;
}
```

Now, the `width` property defines the size of the border box, padding and border width are
subtracted to calculate the available space for the content.

## Include Custom Fonts

You can include custom fonts in different ways:

- find a font on [google fonts](fonts.google.com) and use the `@import` snippet and paste it to the
  top of your css file:
  ```css
  @import url('https://fonts.googleapis.com/css2?family=Red+Hat+Mono:wght@300;			400;500;700&display=swap');
  ```
- use the provided HTML code to add the font via the `link` element in the `head` of your HTML file:

  ```html
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
  	href="https://fonts.googleapis.com/css2?family=Bangers&family=Montserrat&display=swap"
  	rel="stylesheet"
  />
  ```

- download any font and include it as a `font-family`

  ```css
  @font-face {
  	font-family: 'Name of the font';
  	src: url('path/to-the/font.woff');
  }
  ```

## Google Fonts
1. download font via [google webfonts helper](https://google-webfonts-helper.herokuapp.com/fonts) into folder "fonts"
2. copy code from google webfonts helper and insert it into css

## CSS Selectors

## Id Selectors
```css
#title {
	color: blue;
}
```

## Attribute Selectors

Attribute selectors are written inside `[...]` square brackets.

- any element with the attribute hidden

  ```css
  [hidden] {
  	...;
  }
  ```

- all links which open a new tab:

  ```css
  [target='_blank'] {
  	...;
  }
  ```

- all elements with the class `card` and the attribute `role="list"`

  ```css
  .card[role='list'] {
  	...;
  }
  ```

[MDN web docs: Attribute-selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors).
## Pseudo Classes

Style an HTML element differently when it is in a specific state. These are added to a selector and start with a **:** colon. 

- hovered elements

  ```css
  h2:hover {
  	...;
  }
  ```

- active elements like a pressed button

  ```css
  button:active {
  	...;
  }
  ```

- links that have been visited

  ```css
  a:visited {
  	...;
  }
  ```

- form input that has received focus.

  ```css
  input:focus {
  	...;
  }
  ```

- elements which are the first child in another element

  ```css
  li:first-child {
  	...;
  }
  ```

- elements which are the nth child in another element. **n** is the argument that you can replace
  for example with a number or the words **even** and **odd**.

  ```css
  li:nth-child(n) {
  	...;
  }
  ```

[MDN web docs: Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes).
## Pseudo Elements

Pseudo elements let you style a specific part of the selected elements like the first line of a paragraph, the first-letter, the selection etc. They are written with **::** double colons directly after the original selector.

- this selects the first line of paragraphs

  ```css
  p::first-line {
  	...;
  }
  ```

- this creates pseudo elements as the first child of the selected elements

  ```css
  a::before {
  	content: '🌍'; // property needed, can be empty
  }
  ```

- this creates pseudo elements as the last child of the selected elements

  ```css
  a::after {
  	content: '📎'; // property needed, can be empty
  }
  ```

[MDN dev docs: Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
## Combinators

Sometimes it is more efficient to combine multiple selectors instead of defining yet another CSS
class. You can chain together multiple selectors to form rather complex CSS selectors which apply
only in specific cases. In the example above we already combined three selectors: `a`, `:hover` and
`::after`. But there are also other ways to combine selectors:

- `(space)` : a specific element somewhere inside another specific element (regardless of nesting
  level)
  - `h2 span`: any span inside an h2
  - `.card button`: all buttons inside an element with the class "card"
- `>` : targeting a direct descendant of another element
  - `h2>span`: all spans which are direct children of an h2
  - `.card>button`: all buttons which are direct children of an element with the class "card"
- `~` : any later sibling element after another element
  - `h2~span`: any span which is a later sibling of an h2
- `+` : the direct sibling element after another element
  - `.card+button`: a button coming directly after an element with the class "card"

Many combinators can be chained. Can you figure out which element would be styled by the following
selector?

```css
body section > ul[role='list'] > li::before {
	...;
}
```


## Links
- [MDN web docs: CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#index)
- [google webfonts helper](https://google-webfonts-helper.herokuapp.com/fonts)

- [Common CSS Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Properties_Reference)
- [MDN web docs: CSS - First Steps](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps)
- [Styling text](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text)
- [CSS Tricks: Box-sizing](https://css-tricks.com/box-sizing/)
- [Josh Comeau: Surprising truth about pixels and accessibility](https://www.joshwcomeau.com/css/surprising-truth-about-pixels-and-accessibility/)
- [rem/px calculator](https://nekocalc.com/de/px-zu-rem-umrechner)

- [MDN web docs: Attribute-selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)
- [MDN web docs: Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
- [MDN web docs: Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
