# ASCII

American Standard Code for Information Interchange is a 7-bit character encoding standard developed in the 1960s to represent 128 characters—including English letters (a-z, A-Z), digits (0-9), punctuation, and control codes—as numerical values. It acts as a foundational, universal language for computers to store and exchange text. [^1]

<h3>Input word to check ASCII number:</h3>
<textarea id="input" name="input" placeholder="Type character here..." cols="50"></textarea>
<button onclick="changeAscii()" style="border: 1px solid white; padding:4px; color: white;background-color: blue">Translate</button>
<h3>Output:</h3>
<textarea id="outputText" rows="4" cols="50" readonly></textarea>

[^1]: [https://en.wikipedia.org/wiki/ASCII](https://en.wikipedia.org/wiki/ASCII)

<script>
    function changeAscii() {
        let text = document.getElementById('input').value;
        let asciied = "";
        for (let i = 0; i < text.length; i++) {
            asciied += (`Character: ${text[i]}, ASCII: ${text.charCodeAt(i)}\n`);
        }
        document.getElementById('outputText').value = asciied;
    }
</script>
