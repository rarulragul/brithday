<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday ANUSRI</title>

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Poppins',sans-serif;
}

body{
background:linear-gradient(135deg,#ff4e8a,#7b2ff7);
overflow:hidden;
height:100vh;
color:white;
text-align:center;
}

.page{
display:none;
height:100vh;
justify-content:center;
align-items:center;
flex-direction:column;
padding:20px;
}

.active{
display:flex;
}

#gift{
font-size:150px;
cursor:pointer;
animation:bounce 1s infinite;
}

#count{
font-size:120px;
font-weight:bold;
}

#birthdayTitle{
font-size:60px;
color:gold;
text-shadow:0 0 20px #fff;
animation:glow 1s infinite alternate;
}

#cake{
font-size:150px;
animation:drop 2s ease;
}

#wish{
max-width:800px;
font-size:24px;
line-height:1.8;
margin-top:20px;
}

#slide{
width:300px;
height:400px;
border-radius:20px;
object-fit:cover;
box-shadow:0 0 25px white;
margin-top:20px;
}

.heart{
position:absolute;
font-size:25px;
animation:fall 5s linear forwards;
}

@keyframes bounce{
0%,100%{transform:translateY(0);}
50%{transform:translateY(-20px);}
}

@keyframes glow{
from{text-shadow:0 0 10px white;}
to{text-shadow:0 0 30px yellow;}
}

@keyframes drop{
from{transform:translateY(-500px);}
to{transform:translateY(0);}
}

@keyframes fall{
from{transform:translateY(-50px);}
to{transform:translateY(110vh);}
}
</style>
</head>

<body>

<audio autoplay loop>
<source src="birthday-song.mp3" type="audio/mpeg">
</audio>

<div id="page1" class="page active">
<div id="gift">🎁</div>
<h2>Click The Gift</h2>
</div>

<div id="page2" class="page">
<div id="count">5</div>
</div>

<div id="page3" class="page">
<h1 id="birthdayTitle">🎉 HAPPY BIRTHDAY ANUSRI 🎉</h1>
</div>

<div id="page4" class="page">
<div id="cake">🎂</div>

<div id="wish"></div>

<img id="slide" src="wish1.jpg">

<br><br>

<h2>💖 Thank You ANUSRI 💖</h2>
<h3>Made With ❤️ Especially For You</h3>
</div>

<script>

const gift=document.getElementById("gift");

gift.onclick=()=>{

document.getElementById("page1").classList.remove("active");
document.getElementById("page2").classList.add("active");

let count=5;

let timer=setInterval(()=>{

count--;

document.getElementById("count").innerHTML=count;

if(count==0){

clearInterval(timer);

document.getElementById("page2").classList.remove("active");
document.getElementById("page3").classList.add("active");

setTimeout(()=>{

document.getElementById("page3").classList.remove("active");
document.getElementById("page4").classList.add("active");

typeWish();
startHearts();

},3000);
}

},1000);

}

const text=`

Many happy returns of the day.

Hope you feel nothing but loved and appreciated throughout the day and year.

May God bless you and guide you to fulfil all your dreams.

Happy Birthday ANUSRI ❤️🎂✨

`;

function typeWish(){

let i=0;

let speed=40;

function typing(){

if(i<text.length){

document.getElementById("wish").innerHTML+=text.charAt(i);

i++;

setTimeout(typing,speed);

}

}

typing();

}

const photos=[
"wish1.jpg",
"wish2.jpg",
"wish3.jpg",
"wish4.jpg"
];

let current=0;

setInterval(()=>{

current=(current+1)%photos.length;

document.getElementById("slide").src=photos[current];

},3000);

function startHearts(){

setInterval(()=>{

let heart=document.createElement("div");

heart.classList.add("heart");

heart.innerHTML="❤️";

heart.style.left=Math.random()*100+"vw";

heart.style.fontSize=(20+Math.random()*30)+"px";

document.body.appendChild(heart);

setTimeout(()=>{
heart.remove();
},5000);

},300);

}

function firework(){

for(let i=0;i<100;i++){

let spark=document.createElement("div");

spark.innerHTML="✨";

spark.style.position="absolute";

spark.style.left=Math.random()*100+"vw";

spark.style.top=Math.random()*100+"vh";

spark.style.fontSize="30px";

document.body.appendChild(spark);

setTimeout(()=>{
spark.remove();
},2000);

}

}

setInterval(firework,2500);

</script>

</body>
</html>
