<!DOCTYPE html>
<html lang="ms">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>AdamPerodua | Perodua Ampang</title>

<style>
*{box-sizing:border-box}

body{
margin:0;
font-family:Arial,sans-serif;
background:#f4f7fa;
color:#111;
}

header{
background:#071018;
color:white;
padding:16px;
position:sticky;
top:0;
z-index:10;
}

.nav{
max-width:1100px;
margin:auto;
display:flex;
justify-content:space-between;
align-items:center;
}

.logo{
font-size:25px;
font-weight:900;
}

.sub{
font-size:12px;
color:#aaa;
margin-top:3px;
}

.wa{
background:#20c866;
color:white;
text-decoration:none;
padding:11px 15px;
border-radius:12px;
font-weight:bold;
}

.hero{
background:linear-gradient(135deg,#071018,#19364c);
color:white;
padding:40px 18px;
}

.hero h1{
font-size:42px;
margin:0 0 10px;
}

.hero p{
color:#ccd5dc;
}

.container{
max-width:1100px;
margin:auto;
padding:25px 18px 60px;
}

.tabs{
display:flex;
gap:8px;
overflow:auto;
margin-bottom:20px;
}

.tabs button{
border:1px solid #ddd;
background:white;
padding:10px 16px;
border-radius:20px;
font-weight:bold;
white-space:nowrap;
}

.tabs button.active{
background:#071018;
color:white;
}

.viewer{
background:white;
border-radius:22px;
overflow:hidden;
border:1px solid #ddd;
}

.viewer-top{
padding:15px;
display:flex;
justify-content:space-between;
}

.badge{
background:#071018;
color:white;
padding:8px 12px;
border-radius:20px;
font-size:12px;
font-weight:bold;
}

.stage{
height:330px;
background:linear-gradient(145deg,#e8eef2,#fff);
display:flex;
align-items:center;
justify-content:center;
position:relative;
}

.car{
font-size:120px;
}

.arrow{
position:absolute;
top:50%;
transform:translateY(-50%);
width:45px;
height:45px;
border:0;
border-radius:50%;
background:#071018;
color:white;
font-size:25px;
}

.left{left:15px}
.right{right:15px}

.hint{
text-align:center;
padding:10px;
font-size:12px;
color:#687580;
}

.grid{
display:grid;
grid-template-columns:1.2fr .8fr;
gap:18px;
margin-top:18px;
}

.card{
background:white;
padding:20px;
border-radius:22px;
border:1px solid #ddd;
}

.variants{
display:flex;
gap:8px;
overflow:auto;
padding:10px 0;
}

.variant{
border:1px solid #ddd;
background:white;
padding:10px 13px;
border-radius:12px;
font-weight:bold;
white-space:nowrap;
}

.variant.active{
background:#071018;
color:white;
}

.price{
font-size:32px;
font-weight:900;
margin-top:10px;
}

.rebate{
color:#079447;
font-weight:bold;
margin:8px 0 15px;
}

.specs{
display:grid;
grid-template-columns:1fr 1fr;
gap:8px;
}

.spec{
background:#f4f7f9;
padding:12px;
border-radius:12px;
}

.spec small{
display:block;
color:#777;
}

.spec b{
font-size:14px;
}

.buttons{
display:flex;
gap:8px;
margin-top:18px;
}

.buttons a{
flex:1;
text-align:center;
padding:14px;
border-radius:12px;
text-decoration:none;
font-weight:bold;
}

.green{
background:#20c866;
color:white;
}

.dark{
background:#071018;
color:white;
}

input,select{
width:100%;
padding:13px;
margin:6px 0 12px;
border:1px solid #ccd5dc;
border-radius:10px;
font-size:16px;
}

.monthly{
font-size:32px;
font-weight:900;
margin:10px 0;
}

footer{
background:#071018;
color:#ccd5dc;
text-align:center;
padding:30px 15px;
}

@media(max-width:750px){
.grid{
grid-template-columns:1fr;
}

.hero h1{
font-size:34px;
}

.stage{
height:280px;
}
}
</style>
</head>

<body>

<header>

<div class="nav">

<div>
<div class="logo">AdamPerodua</div>
<div class="sub">
Perodua Ampang • Mudah • Cepat • Senang
</div>
</div>

<a class="wa"
href="https://wa.me/60164542974?text=Hi%20Adam%2C%20saya%20nak%20quotation%20Perodua."
target="_blank">
WhatsApp Adam
</a>

</div>

</header>


<section class="hero">

<div class="container">

<h1>🚗 Pilih Perodua Anda</h1>

<p>
Variant • Harga • Spesifikasi • Rebate • Ansuran
</p>

</div>

</section>


<main class="container">

<div class="tabs" id="tabs"></div>

<div id="app"></div>

</main>


<footer>

<b>AdamPerodua</b>

<br>

Perodua Ampang • Fast Approval • Ready Stock

<br>

📲 016-454 2974

</footer>


<script>

const cars={

AXIA:[
["1.0 G","RM33,900","D-CVT","998 cc","25.3 km/L","2 airbags"],
["1.0 X","RM38,500","D-CVT","998 cc","25.3 km/L","2 airbags"],
["1.0 SE","RM43,000","D-CVT","998 cc","27.4 km/L","2 airbags"],
["1.0 AV","RM49,000","D-CVT","998 cc","27.4 km/L","6 airbags"]
],

BEZZA:[
["1.0 G Manual","RM34,580","5MT","998 cc","22.8 km/L","2 airbags"],
["1.0 G Auto","RM36,580","4 E-AT","998 cc","21.3 km/L","2 airbags"],
["1.3 X","RM43,980","4 E-AT","1,329 cc","21.0 km/L","2 airbags"],
["1.3 AV","RM49,980","4 E-AT","1,329 cc","22.0 km/L","2 airbags"]
],

MYVI:[
["1.3 G","RM46,500","D-CVT","1,329 cc","22.2 km/L","4 airbags"],
["1.5 X","RM50,900","D-CVT","1,496 cc","21.1 km/L","4 airbags"],
["1.5 H","RM54,900","D-CVT","1,496 cc","21.1 km/L","6 airbags"],
["1.5 AV","RM59,900","D-CVT","1,496 cc","21.1 km/L","6 airbags"]
],

ATIVA:[
["1.0 X","RM62,500","D-CVT","998 cc Turbo","18.9 km/L","6 airbags"],
["1.0 H","Semak Quote","D-CVT","998 cc Turbo","18.9 km/L","6 airbags"],
["1.0 AV","Semak Quote","D-CVT","998 cc Turbo","18.9 km/L","6 airbags"]
],

ALZA:[
["1.5 X","RM62,500","D-CVT","1,496 cc","22.0 km/L","6 airbags"],
["1.5 H","RM68,000","D-CVT","1,496 cc","22.0 km/L","6 airbags"],
["1.5 AV","RM75,500","D-CVT","1,496 cc","22.0 km/L","6 airbags"]
],

ARUZ:[
["1.5 X","RM72,900","4 E-AT","1,496 cc","15.6 km/L","6 airbags"],
["1.5 AV","Semak Quote","4 E-AT","1,496 cc","15.6 km/L","6 airbags"]
],

TRAZ:[
["1.5 X","RM76,100","D-CVT","1,496 cc","21.3 km/L","6 airbags"],
["1.5 H","RM81,100","D-CVT","1,496 cc","21.3 km/L","6 airbags"],
["1.5 H 2-Tone","RM82,000","D-CVT","1,496 cc","21.3 km/L","6 airbags"]
]

};


let model="MYVI";

let variant=0;


function whatsapp(){

let v=cars[model][variant][0];

return "https://wa.me/60164542974?text="+
encodeURIComponent(
"Hi Adam, saya berminat Perodua "+model+
" "+v+
". Boleh bagi quotation & rebate terkini?"
);

}


function draw(){

let tabs=document.getElementById("tabs");

tabs.innerHTML="";

Object.keys(cars).forEach(function(x){

let b=document.createElement("button");

b.innerText=x;

if(x==model)b.className="active";

b.onclick=function(){

model=x;

variant=0;

draw();

};

tabs.appendChild(b);

});


let v=cars[model][variant];

document.getElementById("app").innerHTML=`

<div class="viewer">

<div class="viewer-top">

<span class="badge">
🔄 360° VIEWER
</span>

<span>
Swipe / drag untuk pusing
</span>

</div>


<div class="stage">

<button class="arrow left"
onclick="prev()">‹</button>

<div class="car">
🚗
</div>

<button class="arrow right"
onclick="next()">›</button>

</div>


<div class="hint">

Nanti kita masukkan 36 gambar untuk
360° sebenar.

</div>

</div>


<div class="grid">


<div class="card">

<h2>Perodua ${model}</h2>


<div class="variants">

${cars[model].map(function(x,i){

return `

<button
class="variant ${i==variant?"active":""}"
onclick="variant=${i};draw()">

${x[0]}

</button>

`;

}).join("")}

</div>


<div class="price">
${v[1]}
</div>


<div class="rebate">
🎁 Rebate Adam
</div>


<div class="specs">

<div class="spec">
<small>Transmisi</small>
<b>${v[2]}</b>
</div>

<div class="spec">
<small>Enjin</small>
<b>${v[3]}</b>
</div>

<div class="spec">
<small>Fuel</small>
<b>${v[4]}</b>
</div>

<div class="spec">
<small>Airbags</small>
<b>${v[5]}</b>
</div>

</div>


<div class="buttons">

<a class="green"
href="${whatsapp()}"
target="_blank">
📲 WhatsApp Adam
</a>

<a class="dark"
href="tel:+60164542974">
☎️ Call
</a>

</div>

</div>


<div class="card">

<h2>🧮 Kira Ansuran</h2>

<label>Harga Kereta</label>

<input
id="price"
type="number"
value="${getPrice(v[1])}"
oninput="calculate()">


<label>Deposit</label>

<input
id="deposit"
type="number"
value="0"
oninput="calculate()">


<label>Kadar Flat (%)</label>

<input
id="rate"
type="number"
value="3"
step="0.01"
oninput="calculate()">


<label>Tempoh</label>

<select id="years"
onchange="calculate()">

<option>9</option>
<option>8</option>
<option>7</option>
<option>6</option>
<option>5</option>

</select>


<div
id="monthly"
class="monthly">

RM0/bulan

</div>


<div class="buttons">

<a
class="green"
href="${whatsapp()}"
target="_blank">

Dapatkan Quotation

</a>

</div>

</div>

</div>

`;

calculate();

}


function getPrice(x){

let n=parseFloat(
x.replace(/[^0-9.]/g,"")
);

return n||0;

}


function calculate(){

let price=Number(
document.getElementById("price").value
)||0;

let deposit=Number(
document.getElementById("deposit").value
)||0;

let rate=
(Number(
document.getElementById("rate").value
)||0)/100;

let years=Number(
document.getElementById("years").value
);

let loan=Math.max(
0,
price-deposit
);

let monthly=
(loan+(loan*rate*years))/
(years*12);

document.getElementById("monthly").innerText=
"RM"+
Math.round(monthly).toLocaleString()+
"/bulan";

}


function next(){

}

function prev(){

}


draw();

</script>

</body>
</html>