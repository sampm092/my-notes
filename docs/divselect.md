# Selecting Div

## First Div

!!! question "Pertanyaan"
    How to select the first div in a class with css?

You can select the first **div** inside a class using the CSS pseudo-class **_:first-of-type_** or **_:first-child_**, depending on what exactly you need.

### Case 1: First-of-type

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

### Case 2: First-child

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

### Case 3: .DivName:first-of-type
Select the first .myDiv among multiple with the same class

If you have multiple elements with the same class and you want only the first one:
``` css
.myDiv:first-of-type {
  background-color: pink;
}
```
…but note: this works only if all .myDiv elements are the same type (e.g., all <*div*>).
If you want literally the first .myDiv regardless of type, you can’t do that purely in CSS — you’d need JavaScript for that.

**Example** <br>
We'll use:
``` html
<section>
  <div class="myDiv">FIRST .myDiv (this one is selected)</div>
  <div class="myDiv">Second .myDiv</div>
  <div class="myDiv">Third .myDiv</div>
</section>
```
```css
.myDiv:first-of-type {
  background-color: gold;
  padding: 10px;
}
```

Result:
<section style="border: 1px solid green"> 
<style>
  .myDiv:first-of-type {
    background-color: gold;
    padding: 10px;
  }
</style>
  <div class="myDiv">FIRST .myDiv (this one is selected)</div>
  <div class="myDiv">Second .myDiv</div>
  <div class="myDiv">Third .myDiv</div>
</section>

!!! info "Why this works?"
    ***:first-of-type*** means “first element of this tag type” <br>
    All ***.myDiv*** elements are <*div*> <br>
    So the first <*div*> that also has ***.myDiv*** gets selected <br>
    Result: only the first ***.myDiv*** is styled.

But remember...
!!! danger "Important limitation (VERY COMMON CONFUSION)"
    If there’s another <*div*> before it, this will NOT work:
    ``` html
    <section>
        <div>I'm a div but NOT .myDiv</div>
        <div class="myDiv">❌ This will NOT be selected</div>
        <div class="myDiv">Second .myDiv</div>
    </section>
    ```


Why?
Because ***:first-of-type*** sees that the first <*div*> already exists — even without the class. <br>
There is NO pure CSS selector for: <br>
“Select the first element with class ***.myDiv*** regardless of tag or siblings” <br>
CSS simply can’t do that yet.