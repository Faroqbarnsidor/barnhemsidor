# barnhemsidor<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Barnsidor</title>
<style>
body{font-family:Arial;background:#eef2ff;text-align:center;}
.box{background:white;padding:20px;border-radius:14px;max-width:500px;margin:auto;margin-top:40px;}
input,textarea{width:100%;padding:10px;margin:10px 0;}
button{background:#4f46e5;color:white;padding:12px;border:none;border-radius:10px;font-size:16px;}
</style>
</head>
<body>

<div class="box">
<h2>Skapa din egen hemsida</h2>
<input id="titel" placeholder="Min rubrik">
<textarea id="text" placeholder="Skriv om dig själv"></textarea>
<input id="bild" placeholder="Klistra in en bildlänk">
<button onclick="create()">Skapa min sida</button>
<p id="link"></p>
</div>

<script>
function create(){
let t = titel.value;
let tx = text.value;
let b = bild.value;

let page = `
<!DOCTYPE html><html><body style="font-family:Arial;text-align:center">
<h1>${t}</h1>
<img src="${b}" width="200">
<p>${tx}</p>
</body></html>`;

let blob = new Blob([page],{type:"text/html"});
let url = URL.createObjectURL(blob);

link.innerHTML = `<a href="${url}" target="_blank">Öppna min hemsida</a>`;
}
</script>
</body>
</html>
