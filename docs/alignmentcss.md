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

Yang mempengaruhi main axis → justify-\* <br>
Yang mempengaruhi cross axis → align-\*

Jika flex-direction: row/baris, maka main = horizontal dan cross = vertical  <br>
<figure markdown="span">
  ![Image title](/assets/flex-row.webp)
</figure>
<!-- <img src="assets/flex-row.webp"> <br> -->
Sementara jika flex-direction: column/kolom, maka main = vertical dan cross = horizontal <br>
<figure markdown="span">
  ![Image title](/assets/flex-col.webp)
</figure>

2️⃣ Who is being aligned?

| Level       | Meaning                               |
| ----------- | ------------------------------------- |
| `*-content` | Aligns **the whole group of items**   |
| `*-items`   | Aligns **all items inside container** |
| `*-self`    | Aligns **one specific item**          |

## Align
Menggunakan contoh yang diambil dari [w3school](https://www.w3schools.com/) :fontawesome-solid-copyright:
### Align-content
Align-content adalah properti CSS yang mengatur bagaimana multiple lines dari flex items didistribusikan secara vertikal di dalam flex container (pada sumbu cross axis).

Fungsi Utama:
<li>Mengatur distribusi ruang antar baris (lines) dalam flex container yang memiliki wrap</li>
<li>Hanya berpengaruh jika flex container memiliki lebih dari satu baris</li>
<li>Tidak berpengaruh pada single-line flex containers</li>
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
    <div style="width: 200px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: start;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>

=== "Center"
    ```css
    align-content: center;
    ```
    <div style="width: 200px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: center;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>

=== "End"
    ```css
    align-content: end;
    ```
    <div style="width: 200px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: end;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>

=== "Space-Between"
    ```css
    align-content: space-between;
    ```
    <div style="width: 200px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: space-between;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>

=== "Space-Around"
    ```css
    align-content: space-around;
    ```
    <div style="width: 200px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: space-around;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>

=== "Space-Evenly"
    ```css
    align-content: space-evenly;
    ```
    <div style="width: 200px;height: 300px;border: 1px solid #c3c3c3;display: flex;flex-wrap: wrap;
    align-content: space-evenly;background-color:white">
        <div style="background-color:coral; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:lightblue; width: 70px;height: 70px;border:1px solid black"></div>
        <div style="background-color:pink; width: 70px;height: 70px;border:1px solid black"></div>
    </div>

### Align-items
Align-items adalah properti CSS yang mengatur bagaimana flex items disusun secara vertikal di dalam flex container (pada sumbu cross axis). <br>

Fungsi Utama:
<li>Mengontrol penjajaran semua item di dalam flex container secara bersamaan pada sumbu tegak lurus (cross axis)</li>
<li>Diterapkan pada flex container, bukan pada individual items</li>
Untuk uji coba, kode yang digunakan:

```css
#main {
  width: 220px;
  height: 300px;
  border: 1px solid black; 
  display: flex;
  align-items: [yang diuji];
}

#main div {
  flex: 1;
  border: 1px solid black;
  display: flex;
}
```

```html

// Main
<div id="main">
  <div style="background-color:coral;min-height:30px;">RED</div>
  <div style="background-color:lightblue;min-height:50px;">BLUE</div>  
  <div style="background-color:lightgreen;min-height:190px;">Green div with more content.</div>
</div>
```
=== "Start"
    ```css
    align-items: start;
    ```
    <div style="background-color:white;color:black;width: 220px;height: 300px;border: 1px solid black; display: flex;align-items: start;">
        <div style="background-color:coral;min-height:30px;flex: 1;border: 1px solid black;display: flex;">RED</div>
        <div style="background-color:lightblue;min-height:50px;flex: 1;border: 1px solid black;display: flex;">BLUE</div>  
        <div style="background-color:lightgreen;min-height:190px;flex: 1;border: 1px solid black;display: flex;">Green div with more content.</div>
    </div>

=== "Center"
    ```css
    align-items: center;
    ```
    <div style="background-color:white;color:black;width: 220px;height: 300px;border: 1px solid black; display: flex;align-items: center;">
        <div style="background-color:coral;min-height:30px;flex: 1;border: 1px solid black;display: flex;">RED</div>
        <div style="background-color:lightblue;min-height:50px;flex: 1;border: 1px solid black;display: flex;">BLUE</div>  
        <div style="background-color:lightgreen;min-height:190px;flex: 1;border: 1px solid black;display: flex;">Green div with more content.</div>
    </div>

=== "End"
    ```css
    align-items: end;
    ```
    <div style="background-color:white;color:black;width: 220px;height: 300px;border: 1px solid black; display: flex;align-items: end;">
        <div style="background-color:coral;min-height:30px;flex: 1;border: 1px solid black;display: flex;">RED</div>
        <div style="background-color:lightblue;min-height:50px;flex: 1;border: 1px solid black;display: flex;">BLUE</div>  
        <div style="background-color:lightgreen;min-height:190px;flex: 1;border: 1px solid black;display: flex;">Green div with more content.</div>
    </div>

=== "Stretch"
    ```css
    align-items: stretch;
    ```
    <div style="background-color:white;color:black;width: 220px;height: 300px;border: 1px solid black; display: flex;align-items: stretch;">
        <div style="background-color:coral;min-height:30px;flex: 1;border: 1px solid black;display: flex;">RED</div>
        <div style="background-color:lightblue;min-height:50px;flex: 1;border: 1px solid black;display: flex;">BLUE</div>  
        <div style="background-color:lightgreen;min-height:190px;flex: 1;border: 1px solid black;display: flex;">Green div with more content.</div>
    </div>

### Align-self
Align-self adalah properti CSS yang mengatur penjajaran individu sebuah item di dalam flex container secara vertikal (pada sumbu cross axis).

Fungsi Utama:<br>
<li>Meng-override penjajaran default dari properti align-items yang diterapkan pada container</li>
<li>Mengontrol posisi item secara individual di dalam flex container</li>
Untuk uji coba dilakukan pada satu div saja, kode yang digunakan:

```css
#main {
    width: 220px;
    height: 300px;
    border: 1px solid black;
    display: flex;
    align-items: flex-start;
}

#main div {
    flex: 1;    
}

#myBlueDiv {
    align-self: [yang diuji]; 
}
```

```html
<div id="main">
  <div style="background-color:coral;">RED</div>
  <div style="background-color:lightblue;" id="myBlueDiv">BLUE</div>  
  <div style="background-color:lightgreen;">Green div with more content.</div>
</div>
```

=== "Start"
    ```css
    align-self: start;
    ```
    <div style="width: 220px;height: 300px;border: 1px solid black;display: flex;align-items: flex-start;background-color: white;color:black">
        <div style="background-color:coral;flex: 1;">RED</div>
        <div style="background-color:lightblue;flex: 1;align-self: start;" id="myBlueDiv">THIS</div>  
        <div style="background-color:lightgreen;flex: 1;">Green div with more content.</div>
    </div>  
=== "Center"
    ```css
    align-self: center;
    ```
    <div style="width: 220px;height: 300px;border: 1px solid black;display: flex;align-items: flex-start;background-color: white;color:black">
        <div style="background-color:coral;flex: 1;">RED</div>
        <div style="background-color:lightblue;flex: 1;align-self: center;" id="myBlueDiv">THIS</div>  
        <div style="background-color:lightgreen;flex: 1;">Green div with more content.</div>
    </div>  
=== "End"
    ```css
    align-self: end;
    ```
    <div style="width: 220px;height: 300px;border: 1px solid black;display: flex;align-items: flex-start;background-color: white;color:black">
        <div style="background-color:coral;flex: 1;">RED</div>
        <div style="background-color:lightblue;flex: 1;align-self: end;" id="myBlueDiv">THIS</div>  
        <div style="background-color:lightgreen;flex: 1;">Green div with more content.</div>
    </div>  
=== "Stretch"
    ```css
    align-self: stretch;
    ```
    <div style="width: 220px;height: 300px;border: 1px solid black;display: flex;align-items: flex-start;background-color: white;color:black">
        <div style="background-color:coral;flex: 1;">RED</div>
        <div style="background-color:lightblue;flex: 1;align-self: stretch;" id="myBlueDiv">THIS</div>  
        <div style="background-color:lightgreen;flex: 1;">Green div with more content.</div>
    </div>  