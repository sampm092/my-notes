# Selecting Div

## First Div
!!! question "Pertanyaan"
    How to select the first div in a class with css?

You can select the first **div** inside a class using the CSS pseudo-class ***:first-of-type*** or ***:first-child***, depending on what exactly you need.

### Case 1: 
Select the first <*div*> inside an element with a certain class
```
.container div:first-of-type {
    background-color: yellow;
}
```

This selects the first <*div*> that appears inside any element with class .container. <br>
It doesn’t matter if there are other elements (like <*p*> or <*span*>) before it.

**Example** <br>
We'll use: 
``` css
container div:first-of-type {
  background-color: darkgreen;
}
```

``` html
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