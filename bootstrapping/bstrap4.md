### Bootstrap and JQuery

- some notes from the freecodecamp at https://www.freecodecamp.org/learn

- Bootstrap uses a responsive 12-column grid system, which makes it easy to put elements into rows and specify each element's relative width. Most of Bootstrap's classes can be applied to a div element.
Bootstrap has different column width attributes that it uses depending on how wide the user's screen is. For example, phones have narrow screens, and laptops have wider screens.


- `col-md-*` class where `md` means medium, `xs` means extra small etc and  `*` is a number that specifies how many columns wide the element should be.

- You can use spans to create inline elements
- `btn-block` class to make a button fill an entire row

- By using the inline **span** element, you can put several elements on the same line, and even style different parts of the same line differently.

- Bootstrap uses a responsive grid system, which makes it easy to put elements into rows and specify each element's relative width. Most of Bootstrap's classes can be applied to a div element.

- Font Awesome is a convenient library of icons. These icons can be webfonts or vector graphics. These icons are treated just like fonts. You can specify their size using pixels, and they will assume the font size of their parent HTML elements.

You can include Font Awesome in any app by adding the following code to the top of your HTML:

<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.8.1/css/all.css" integrity="sha384-50oBUHEmvpQ+1lW4y57PTFmhCaXp0ML5d60M1M7uH2+nqUivzIebhndOJK28anvf" crossorigin="anonymous">


The `i` element was originally used to make other elements italic, but is now commonly used for icons. You can add the Font Awesome classes to the i element to turn it into an icon, for example:

`<i class="fas fa-info-circle"></i>`

Note that the span element is also acceptable for use with icons.

You can use Bootstrap's col-xs-* classes on form elements, too! For example so that radio buttons or checkboxes will be evenly spread out across the page, regardless of how wide the screen resolution is.

- Bootstrap has a class called `well` that can create a visual sense of depth for your columns.

- Not every class needs to have corresponding CSS. Sometimes we create classes just for the purpose of selecting these elements more easily using jQuery.

- In addition to class attributes, you can give each of your elements an `id` attribute.
Each id must be unique to a specific element and used only once per page

- Using JQuery we can modify HTML elements without needing to actually change them in HTML.

---

## Introduction to jQuery
https://www.w3schools.com/jquery/jquery_get_started.asp

jQuery is one of the many libraries for JavaScript. It is designed to simplify scripting done on the client side. jQuery's most recognizable characteristic is its dollar sign `($)` syntax. With it, you can easily manipulate elements, create animations and handle input events.
First, add a script element at the top of your page. 
Your browser will run any JavaScript inside a script element, including jQuery.

Inside your script element, add this code: 
```javascript
`$`(document).ready(function() { 
    
 });
```

The important thing to know is that code you put inside this function will run as soon as your browser has loaded your page.
This is important because without your document ready function, your code may run before your HTML is rendered, which would cause bugs.

- All jQuery functions start with a `$`, usually referred to as a dollar sign operator, or as bling.

- jQuery often selects an HTML element with a selector, then does something to that element.


We selected them with `$`("button"), then we added some CSS classes to them with .addClass("animated bounce");
```javascript
<script>
  $(document).ready(function() {
    $("button").addClass("animated bounce");
  });
</script>
```

jQuery's `.addClass()` function, which allows you to add classes to elements.

For example, you could make all the elements with the class text-primary shake by adding the following to your document ready function:

`$(".text-primary").addClass("animated shake");`

```javascript
<script>
  $(document).ready(function() {
    $("button").addClass("animated bounce");
    $(".well").addClass("animated shake");
    $("#target3").addClass("animated fadeOut");

  });
</script>
```

Three ways so far of targeting elements: 
- by type: `$`("button"), 
- by class: `$`(".btn"), and 
- by id `$`("#target1").

It is also possible to add multiple classes in a single `.addClass()` call.

- In the same way you can add classes to an element with jQuery's `addClass()` function, you can remove them with jQuery's `removeClass()` function.

```javascript
$("#target2").removeClass("btn-default");
```
- We can also change the CSS of an HTML element directly with jQuery.

- jQuery has a function called .`css()` that allows you to change the CSS of an element.

Here's how we would change its color to blue:

```javascript
$("#target1").css("color", "blue");
```

- NB! This is slightly different from a normal CSS declaration, because the CSS property and its value are in quotes, and separated with a comma instead of a colon.

- You can also change the non-CSS properties of HTML elements with jQuery. For example, you can disable buttons.The button will become grayed-out and can no longer be clicked.

- jQuery has a function called `.prop()` that allows you to adjust the properties of elements.

Here's how you would disable all buttons:

```javascript
$("button").prop("disabled", true);
```
#### jQuery: Change Text Inside an Element Using jQuery

- Using jQuery, you can change the text between the start and end tags of an element. You can even change HTML markup.

- jQuery has a function called `.html()` that lets you add HTML tags and text within an element. Any content previously within the element will be completely replaced with the content you provide using this function.

Here's how you would rewrite and emphasize the text of our heading:
```javascript
$("h3").html("<em>jQuery Playground</em>");
```

- jQuery also has a similar function called `.text()` that only alters text without adding tags. In other words, this function will not evaluate any HTML tags passed to it, but will instead treat it as the text you want to replace the existing content with.

- jQuery has a function called `.remove()` that will remove an HTML element entirely

#### jQuery: Use appendTo to Move Elements with jQuery

- jQuery has a function called `appendTo()` that allows you to select HTML elements and append them to another element.

For example, if we wanted to move target4 from our right well to our left well, we would use:

```javascript
$("#target4").appendTo("#left-well");
```

#### jQuery: Clone an Element Using jQuery
In addition to moving elements, you can also copy them from one place to another.

- jQuery has a function called `clone()` that makes a copy of an element.

For example, if we wanted to copy target2 from our left-well to our right-well, we would use:

```javascript
$("#target2").clone().appendTo("#right-well");
```

This involves sticking two jQuery functions together which is called **function chaining** and it's a convenient way to get things done with jQuery.

#### jQuery: Target the Parent of an Element Using jQuery
- Every HTML element has a parent element from which it inherits properties.

For example, your jQuery Playground h3 element has the parent element of `<div class="container-fluid">`, which itself has the parent body.

- jQuery has a function called `parent()` that allows you to access the parent of whichever element you've selected.

Here's an example of how you would use the parent() function if you wanted to give the parent element of the left-well element a background color of blue:

```javascript
$("#left-well").parent().css("background-color", "blue")
```

#### jQuery: Target the Children of an Element Using jQuery

When HTML elements are placed one level below another they are called children of that element. For example, the button elements in this challenge with the text "#target1", "#target2", and "#target3" are all children of the `<div class="well" id="left-well">` element.

- jQuery has a function called `children()` that allows you to access the children of whichever element you've selected.

Here's an example of how you would use the children() function to give the children of your left-well element the color blue:

```javascript
$("#left-well").children().css("color", "blue")
```

#### jQuery: Target a Specific Child of an Element Using jQuery
Id attributes are very convenient for targeting with jQuery selectors. But you won't always have such neat ids to work with.

Fortunately, jQuery has some other tricks for targeting the right elements.

jQuery uses **CSS Selectors** to target elements. 
- The `target:nth-child(n)` CSS selector allows you to select all the nth elements with the target class or element type.

Here's how you would give the third element in each well the bounce class:

```javascript
$(".target:nth-child(3)").addClass("animated bounce");
```

#### jQuery: Target Even Elements Using jQuery
You can also target elements based on their positions using `:odd` or `:even` selectors.

NB! - Note that jQuery is zero-indexed which means the first element in a selection has a position of 0.

Here's how you would target all the odd elements with class target and give them classes:

```javacript
$(".target:odd").addClass("animated shake");
```

#### jQuery: Use jQuery to Modify the Entire Page


jQuery can target the body element as well.

Here's how we would make the entire body fade out: 
```javascript
$("body").addClass("animated fadeOut");
```


