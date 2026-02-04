# Selecting Div

## First Div

!!! question "Pertanyaan"
How to select the first div in a class with css?

You can select the first **div** inside a class using the CSS pseudo-class **_:first-of-type_** or **_:first-child_**, depending on what exactly you need.

### Case 1:

Select the first <_div_> inside an element with a certain class

```
.container div:first-of-type {
    background-color: yellow;
}
```

This selects the first <_div_> that appears inside any element with class .container. <br>
It doesn’t matter if there are other elements (like <_p_> or <_span_>) before it.

**Example** <br>
We'll use:

```css
container div:first-of-type {
  background-color: darkgreen;
}
```

```html
<div class="container">
  <p>Paragraph</p>
  <div>✅ This div will be selected</div>
  <div>This div won’t</div>
</div>
```

Result:

<div class="container" style="border: 1px solid green">
  <p>Paragraph</p>
  <div style=" background-color: darkgreen;">✅ This div will be selected</div>
  <div>This div won’t</div>
</div>

### Case 2:

Select the first child only if it’s a <_div_>

```css
.container > div:first-child {
  background-color: lightblue;
}
```

This only works if the first child element inside .container is a <_div_>.

**Example** <br>
We'll use:

```css
.container > div:first-child {
  background-color: darkred;
}
```

```html
<div class="container">
  <div>✅ This div will be selected</div>
  <div>This one won’t</div>
</div>
```

Result:

<section>
    <style>
    .container > div:first-child {
        background-color: darkred;
    }
    </style>
    <div class="container" style="border: 1px solid green">
    <div>✅ This div will be selected</div>
    <div>This one won’t</div>
    </div>
</section>

But if the first child is not a div.
Code:
``` html
<div class="container">
    <p>Paragraph first</p>
    <div>🚫 Not selected, because it's not the first child</div>
    <div>Second div</div>
</div>
```

Result:
<section>
    <div class="container" style="border: 1px solid green">
        <p>Paragraph first</p>
        <div>🚫 Not selected, because it's not the first child</div>
        <div>Second div</div>
    </div>
</section>
