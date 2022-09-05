- [HTML structure](#HTML-structure)
  - [List of common HTML elements](#List-of-common-HTML-elements)
  - [List of Semantic HTML elements](#List-of-Semantic-HTML-elements)
  - [Recources](#Recources)
- [HTML Forms](#HTML-Forms)
  - [Basic form setup](#Basic-form-setup)
    - [`<form>` tag](#formtag)
    - [Form field names](#Form-field-names)
    - [Labels](#Labels)
  - [Different types of form fields](#Different-types-of-form-fields)
    - [Text](#Text)
    - [Email](#Email)
    - [Number](#Number)
    - [Date](#Date)
    - [Color](#Color)
    - [Multi-line text](#Multi-line-text)
    - [Select / dropdown menu](#Select-dropdown-menu)
    - [Radio elements](#Radio-elements)
    - [Checkboxes](#Checkboxes)
    - [More form field types](#More-form-field-types)
  - [Buttons](#Buttons)
    - [Submit button](#Submit-button)
    - [Reset button](#Reset-button)
    - [Other buttons](#Other-buttons)
  - [Form structure and a11y](#Form-structure-and-a11y)
  - [Resources](#Resources)
  - [Challenges](#Challenges)

<a name="HTML-structure"></a>

## HTML structure

```html
<!DOCTYPE html>
<html>
  <head>
    … meta information, additional links to CSS / JavaScript files …
  </head>
  <body>
    … elements displayed on the web page …
  </body>
</html>
```

<a name="List-of-common-HTML-elements"></a>

## List of common HTML elements

| element             | meaning                                                      |
| ------------------- | ------------------------------------------------------------ |
| `<head></head>`     | only once per website, includes meta data and linked files   |
| `<body></body>`     | only once per website, includes the html website content     |
| `<h1></h1>`         | only once per website, a level one heading                   |
| `<h2></h2>`         | a level two heading                                          |
| `<p></p>`           | a paragraph                                                  |
| `<a></a>`           | an anchor (link)                                             |
| `<img>`             | an image (self-closing / empty)                              |
| `<form></form>`     | a form element                                               |
| `<input>`           | an input field (self-closing / empty)                        |
| `<button></button>` | a clickable element equipped with some kind of functionality |

<a name="List-of-Semantic-HTML-elements"></a>

## List of Semantic HTML elements

| element                 | meaning                                                                                                             |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `<main></main>`         | only once per website, includes the main content of the page                                                        |
| `<section></section>`   | a generic standalone section of a document                                                                          |
| `<ul></ul>`/`<ol></ol>` | a list of elements with the same structure, only has `<li>` elements as direct children                             |
| `<nav></nav>`           | a navigation bar                                                                                                    |
| `<aside></aside>`       | element representing a portion of a document whose content is only indirectly related to the main content           |
| `<article></article>`   | representing a self-containing part of the website, which is intended to be independently distributable or reusable |
| `<header></header>`     | representing introductory content, typically a group of introductory or navigational aids                           |
| `<footer></footer>`     | typically contains information about the author of the section, copyright data or links to related documents        |

<a name="Recources"></a>

## Links

- [MDN: Introduction to HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML)
- [MDN: Getting started with HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started)
- [HTML **elements** reference on mdn web docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#inline_text_semantics)
- [HTML **attribute** reference on mdn web docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes)
- [**semantic HTML elements** on mdn web docs](https://developer.mozilla.org/en-US/docs/Glossary/Semantics)
- [Emmet cheatsheet](https://coolcheatsheet.com/toolkit/emmet)

<a name="HTML-Forms"></a>

# HTML Forms

## Learning Objectives

- Understanding the purpose and structure of forms
- Knowing most common types of form fields
- Building useable and accessible forms
- Understanding the different types of buttons

---

<a name="Basic-form-setup"></a>

## Basic form setup

<a name="formtag"></a>

### `<form>` tag

The `<form>` tag must be wrapped around the complete form with all elements, that are presented as
form controls to the user.

```html
<form>
  <!-- All form elements inside -->
</form>
```

<a name="Form-field-names"></a>

### Form field names

Forms are created to request information from the user. Each fragment of information (each form
field) requires a unique name. It can be set with the `name` attribute and pairs up with the entered
data, when submitting the form.

```html
<input name="first-name" />
```

<a name="Labels"></a>

### Labels

The `<label>` always goes together with a form field. It provides a caption to let users understand,
what kind of data they are asked to enter.

It is required to define, which label and form field belong together. Use the `for` attribute on the
`<label>` and the `id` attribute on the form field. Their values needs to match.

```html
<label for="first-name">First name</label>
<input name="first-name" id="first-name" />
```

> ❗️ Always add a label to a form field. Otherwise users won't understand the purpose of a field,
> which makes it unusable.
> ❗️ Never use the `placeholder` attribute instead of a label.

---

<a name="Different-types-of-form-fields"></a>

## Different types of form fields

<a name="Text"></a>

### Text

The default `type` for `<input>` elements is `text`. Choose the `type` based on the kind of data the
user is requested to enter. Use `type="text"` when none of the other types is a better fit.

```html
<label for="first-name">First name</label>
<input type="text" name="first-name" id="first-name" />
```

<a name="Email"></a>

### Email

Use `type="email"` to let the user enter an email address. The browser can check automatically,
whether the entered text is a valid email address. .

```html
<label for="email-address">Email address</label>
<input type="email" name="email-address" id="email-address" />
```

<a name="Number"></a>

### Number

Use `type="number"` to let the user enter a number.

```html
<label for="age">Age</label> <input type="age" name="age" id="age" />
```

<a name="Date"></a>

### Date

Use `type="date"` to let the user enter a date with the help of a date picker (calendar) provided by
the browser.

```html
<label for="date-of-birth">Date of birth</label>
<input type="date" name="date-of-birth" id="date-of-birth" />
```

<a name="Color"></a>

### Color

Use `type="color"` to let the user enter a color with the help of a color picker tool provided by
the browser.

```html
<label for="favorite-color">Favorite color</label>
<input type="color" name="favorite-color" id="favorite-color" />
```

<a name="Multi-line-text"></a>

### Multi-line text

Use the tag `<textarea>` to let the user enter longer text with multiple lines.

```html
<label for="personal-message">Personal Message</label>
<textarea name="personal-message" id="personal-message"></textarea>
```

> ❗️ Please be aware that the `<textarea>` tag is not a self-closing as the `<input>` tag

<a name="Select-dropdown-menu"></a>

### Select / dropdown menu

The `<select>` field lets the user choose between different options wrapped into `<option>` tags
that are nested into their parent `<select>` tag - this renders a dropdown menu. Each `<option>` has
a `value` attribute defining the data to be submitted. The option's text presented to the user is
defined between the opening and closing tag

```html
<label for="billing-plan">Billing plan</label>
<select name="billing-plan" id="billing-plan">
  <option value="weekly">Weekly billing</option>
  <option value="monthly">Monthly billing</option>
  <option value="yearly">Monthly billing</option>
</select>
```

<a name="Radio-elements"></a>

### Radio elements

The `<input type="radio" />` element is another way of presenting a choice with different options to
the user. In many situations it can be used as an alternative to `<select>`.

```html
<input
  type="radio"
  name="billing-plan"
  id="billing-plan-weekly"
  value="weekly"
/>
<label for="billing-plan-weekly">Weekly billing</label>

<input
  type="radio"
  name="billing-plan"
  id="billing-plan-monthly"
  value="monthly"
/>
<label for="billing-plan-monthly">Monthly billing</label>

<input
  type="radio"
  name="billing-plan"
  id="billing-plan-yearly"
  value="yearly"
/>
<label for="billing-plan-yearly">Yearly billing</label>
```

> ❗️ The `name` attribute must be equal among all radio elements that refer to the same choice. The
> browser groups them together and ensures only one radio element can be selected at the same time.

<a name="Checkboxes"></a>

### Checkboxes

In contrast to the radio element, `<input type="checkbox" />` presents individual choices, that are
not related to each other. Each choice can either be "on" ("true") or "off" ("false").

```html
<input type="checkbox" name="accept-data-privacy" id="accept-data-privacy" />
<label for="accept-data-privacy">I accept the data privacy agreement </label>

<input
  type="checkbox"
  name="accept-terms-conditions"
  id="accept-terms-conditions"
/>
<label for="accept-terms-conditions">I accept the terms and conditions </label>
```

> ❗️ The `name` attribute must not be equal among the checkbox elements. They are used to represent
> individual choices.
> <a name="More-form-field-types"></a>

### More form field types

The different types of `<input>` elements described above is just a small selection. Please refer to
the [MDN web docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) to see a
complete list of all types with examples.

---

<a name="Buttons"></a>

## Buttons

<a name="Submit-button"></a>

### Submit button

The default `type` for a `<button>` element is `submit`. It is used to let users submit the form's
data after they filled out all fields.

```html
<button type="submit">Send</button>
```

> 💡 Since it's the default, it would work the same without the type attribute:
> `<button>Send</button>`.
> <a name="Reset-button"></a>

### Reset button

A button with `type="reset"` lets the user reset all form fields to the their default value on
click.

```html
<button type="reset">Reset all fields</button>
```

<a name="Other-buttons"></a>

### Other buttons

Since `type="submit"` is the default for `<button>` elements, buttons outside of a `form` element
should be defined with `type="button"` to be semantically correct.

```html
<button type="button">Click here for more information</button>
```

This also applies to buttons with diverging functionality within a form.

---

<a name="Form-structure-and-a11y"></a>

## Form structure and a11y

### Fieldset and Legend

The `<fieldset>` element is used to group multiple fields together. Use the `<legend>` element to
provide a caption for such a group.

```html
<fieldset>
  <legend>Personal information</legend>

  <label for="first-name">First name</label>
  <input type="text" name="first-name" id="first-name" />

  <label for="email">Email address</label>
  <input type="email" name="email" id="email" />
</fieldset>
```

### `aria` labels

#### aria-label

The `aria-label` attribute defines a label for an interactive element. Use it when the accessible
name is missing and there is no content visible in the DOM that can be referenced via the
`aria-labelledby` attribute, e.g. a button with no text but only an icon:

```html
<button aria-label="Close form" onClick="...">
  <svg ...><path ... /></svg>
</button>
```

#### aria-labelledby

The `aria-labelledby` attribute identifies which element labels the element it is applied to. Use
the `id` attribute to create the connection:

```html
<h2 id="title">Personal Information Form</h2>
<form aria-labelledby="title">...</form>
```

#### aria-describedby

The `aria-describedby` attribute allows more verbose information than a label. Use the `id`
attribute to create the connection:

```html
<p id="description">
  We need some personal information about you in order to proceed. Please fill
  in this form so that we can help you.
</p>
<fieldset aria-describedby="description">...</fieldset>
```

<a name="Resources"></a>

## Resources

- [`<form>`: The Form element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)
- [`<input>`: The Input (Form Input) element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
- [Forms Tutorial W3C](https://www.w3.org/WAI/tutorials/forms/)
- [Forms (Web Accessibility Guidelines)](http://web-accessibility.carnegiemuseums.org/code/forms/)

<a name="Challenges"></a>

## Challenges

- [Personal Profile Form a](https://codesandbox.io/s/html-forms-more-input-types-01a-dwr3u2)
- [Personal Profile Form b](https://codesandbox.io/s/html-forms-personal-profile-form-01b-fdhqoo)
- [Forms and A11y a](https://codesandbox.io/s/html-forms-forms-and-a11y-01a-sbm6wh)
- [Forms and A11y b](https://codesandbox.io/s/html-forms-forms-and-a11y-01b-sh8ck6)
- [More input types a](https://codesandbox.io/s/html-forms-personal-profile-form-01a-341u48)
- [More input types b](https://codesandbox.io/s/html-forms-more-input-types-01b-wme8mm)
