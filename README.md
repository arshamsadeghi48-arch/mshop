
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>گالری نقاشی‌های من</title>

<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;700&display=swap" rel="stylesheet">

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
}

body{
font-family:'Vazirmatn',sans-serif;
color:#2d1e12;
min-height:100vh;
padding:20px;
background:linear-gradient(-45deg,#ee7752,#e73c7e,#23a6d5,#23d5ab);
background-size:400% 400%;
animation:gradientFlow 20s ease infinite;
}

@keyframes gradientFlow{
0%{background-position:0% 50%;}
50%{background-position:100% 50%;}
100%{background-position:0% 50%;}
}

header{
text-align:center;
padding:60px 20px 40px;
}

h1{
font-size:3rem;
color:#4a2c8c;
margin-bottom:10px;
}

.tagline{
font-size:1.2rem;
color:#5c4a6e;
max-width:600px;
margin:auto;
}

.gallery{
max-width:1200px;
margin:auto;
display:grid;
grid-template-columns:repeat(auto-fit,minmax(300px,1fr));
gap:30px;
padding-top:40px;
}

.card{
background:white;
border-radius:16px;
overflow:hidden;
box-shadow:0 10px 30px rgba(0,0,0,0.1);
transition:.3s;
position:relative;
opacity:0;
transform:translateY(30px);
animation:fadeInUp 0.8s forwards;
}

.card:hover{
transform:translateY(-10px);
box-shadow:0 20px 45px rgba(0,0,0,0.2);
}

.card img{
width:100%;
height:360px;
object-fit:cover;
cursor:pointer;
}

.info{
padding:20px;
}

.title{
font-size:1.3rem;
margin-bottom:8px;
}

.price{
font-size:1.4rem;
font-weight:bold;
color:#d32f2f;
margin:12px 0;
}

.btn{
display:inline-block;
background:#e1306c;
color:white;
padding:10px 22px;
border-radius:40px;
text-decoration:none;
transition:.25s;
}

.btn:hover{
background:#c13584;
transform:scale(1.05);
}

.sold::after{
content:"فروش رفته";
position:absolute;
top:20px;
right:20px;
background:#e53935;
color:white;
padding:6px 16px;
border-radius:30px;
font-size:.9rem;
}

footer{
text-align:center;
margin-top:60px;
color:#444;
}

/* Lightbox */
#lightbox{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:rgba(0,0,0,0.8);
display:none;
align-items:center;
justify-content:center;
z-index:999;
}

#lightbox-img{
max-width:90%;
max-height:90%;
border-radius:10px;
}

/* انیمیشن ورود */
@keyframes fadeInUp{
0%{
opacity:0;
transform:translateY(30px);
}
100%{
opacity:1;
transform:translateY(0);
}
}

@media(max-width:600px){
h1{font-size:2.2rem;}
.card img{height:300px;}
}

</style>
</head>

<body>

<header>
<h1>نقاشی‌های من</h1>
<p class="tagline">
هر تابلو یه قصه‌ست… اگه دوست داری یکی‌شون خونه‌ی تو رو قشنگ‌تر کنه، بیا تو دایرکت حرف بزنیم 🌸
</p>
</header>

<section class="gallery">

<div class="card" style="animation-delay:0s;">
<img src="https://i.imgur.com/BJFK1Uq.jpg" alt="نقاشی هیچ">
<div class="info">
<h3 class="title">نقاشی هیچ</h3>
<div class="price">700,000 تومان</div>
<a href="https://www.instagram.com/mhnargo?igsh=cHpycG5rNDNsMHo4" class="btn" target="_blank">
پیام در دایرکت اینستاگرام
</a>
</div>
</div>

<div class="card" style="animation-delay:0.2s;">
<img src="https://i.imgur.com/BdacAOL.jpg" alt="تابلو ماه">
<div class="info">
<h3 class="title">تابلو ماه</h3>
<div class="price">1,500,000 تومان</div>
<a href="https://www.instagram.com/mhnargo?igsh=cHpycG5rNDNsMHo4" class="btn" target="_blank">
پیام در دایرکت اینستاگرام
</a>
</div>
</div>

<div class="card sold" style="animation-delay:0.4s;">
<img src="https://i.imgur.com/cWFxxbz.jpg" alt="طلوع در دشت">
<div class="info">
<h3 class="title">طلوع در دشت</h3>
<div class="price">فروش رفته</div>
</div>
</div>

</section>

<!-- Lightbox -->
<div id="lightbox">
<img id="lightbox-img">
</div>

<script>
const images = document.querySelectorAll(".card img");
const lightbox = document.getElementById("lightbox");
const lightboxImg = document.getElementById("lightbox-img");

images.forEach(img=>{
    img.addEventListener("click",()=>{
        lightbox.style.display="flex";
        lightboxImg.src = img.src;
    });
});

lightbox.addEventListener("click",()=>{
    lightbox.style.display="none";
});

// افکت اسکرول
const cards = document.querySelectorAll('.card');

const observer = new IntersectionObserver(entries=>{
  entries.forEach(entry=>{
    if(entry.isIntersecting){
      entry.target.style.animationPlayState = 'running';
    }
  });
},{
  threshold:0.2
});

cards.forEach(card=>{
  card.style.animationPlayState = 'paused';
  observer.observe(card);
});
</script>

<footer>
ساخته شده با عشق و رنگ 🎨  
<br>
دایرکت اینستاگرام:
<a href="https://www.instagram.com/mhnargo?igsh=cHpycG5rNDNsMHo4" target="_blank">@mhnargo</a>
</footer>

</body>
</html>
