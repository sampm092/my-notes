# Alignment Properties for CSS

Alignment Properties menghandle spacing ketika mendesain interface website menggunakan HTML + CSS.
Pada umumnya alignment mempengaruhi element yang menggunakan display flex dan grid.

!!! question "Pertanyaan"
    Apa perbedaan :
    <ul>
    <li>align-(content, items, self)</li>
    <li>justify-(content, items, self)</li>
    <li>place-(content, items, self)</li>
    </ul>

??? info "Tabel Perbedaan"
    Berdasarkan ChatGPT

    | Property            | Axis  | Applies to | Flex | Grid | When it works              |
    | ------------------- | ----- | ---------- | ---- | ---- | -------------------------- |
    | **align-content**   | Cross | Container  | ⚠️   | ✅    | **Multi-line only**        |
    | **align-items**     | Cross | Container  | ✅    | ✅    | Single or multi            |
    | **align-self**      | Cross | Item       | ✅    | ✅    | Overrides `align-items`    |
    | **justify-content** | Main  | Container  | ✅    | ✅    | When there’s extra space   |
    | **justify-items**   | Main  | Container  | ❌    | ✅    | Aligns items in grid cells |
    | **justify-self**    | Main  | Item       | ❌    | ✅    | Grid only                  |
    | **place-content**   | Both  | Container  | ⚠️   | ✅    | Shorthand                  |
    | **place-items**     | Both  | Container  | ❌    | ✅    | Shorthand                  |
    | **place-self**      | Both  | Item       | ❌    | ✅    | Shorthand                  |

1️⃣ Axes

Yang mempengaruhi main axis → justify-\*

Yang mempengaruhi cross axis → align-\*

Kalau flex-direction: row/baris → main = horizontal, cross = vertical  <br>
Sementara flex-direction: column/kolom → main = vertical, cross = horizontal 

2️⃣ Who is being aligned?

| Level       | Meaning                               |
| ----------- | ------------------------------------- |
| `*-content` | Aligns **the whole group of items**   |
| `*-items`   | Aligns **all items inside container** |
| `*-self`    | Aligns **one specific item**          |

## Align
Menggunakan contoh yang diambil dari [w3school](https://www.w3schools.com/) :fontawesome-solid-copyright:
### Align-content
Untuk uji coba, digunakan:

```css
 #main {
  width: 70px;
  height: 300px;
  border: 1px solid #c3c3c3;
  display: flex;
  flex-wrap: wrap;
  align-content: [Yang Diuji];
}

#main div {
  width: 70px;
  height: 70px;
}
```

```html

// Main
<div id="main">
  <div style="background-color:coral;"></div>
  <div style="background-color:lightblue;"></div>
  <div style="background-color:pink;"></div>
</div>
```
=== "Start"
    ```css
    align-content: start;
    ```
    <div style="width: 70px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: start;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>

=== "Center"
    ```css
    align-content: center;
    ```
    <div style="width: 70px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: center;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>

=== "End"
    ```css
    align-content: end;
    ```
    <div style="width: 70px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: end;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>

=== "Space-Between"
    ```css
    align-content: space-between;
    ```
    <div style="width: 70px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: space-between;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>

=== "Space-Around"
    ```css
    align-content: space-around;
    ```
    <div style="width: 70px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: space-around;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>

=== "Space-Evenly"
    ```css
    align-content: space-evenly;
    ```
    <div style="width: 70px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: space-evenly;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>