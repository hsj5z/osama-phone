<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>أسامة فون - متجر إلكتروني</title>
<style>
body {margin:0;font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;background:#0d0d0d;color:#e0e0e0;}
header{background:linear-gradient(90deg,#6a00ff,#00ff88);padding:20px;text-align:center;color:white;font-size:2rem;font-weight:bold;text-shadow:0 0 10px #00ff88,0 0 20px #6a00ff;position:relative;}
.cart{position:absolute;top:20px;left:20px;font-size:1.2rem;background:#111;padding:8px 15px;border-radius:8px;box-shadow:0 0 10px rgba(0,255,136,0.4);cursor:pointer;transition:box-shadow 0.3s ease;}
.cart:hover{box-shadow:0 0 20px rgba(106,0,255,0.6);}
.cart span{color:#00ff88;font-weight:bold;}
nav{display:flex;justify-content:center;background:#111;padding:10px;}
nav a{color:#b3ffec;text-decoration:none;margin:0 15px;font-weight:bold;transition:color 0.3s ease,text-shadow 0.3s ease;}
nav a:hover{color:#00ff88;text-shadow:0 0 10px #6a00ff;}
.hero{text-align:center;padding:50px 20px;background:radial-gradient(circle at center,#1a1a1a,#0d0d0d);}
.hero h1{color:#6a00ff;text-shadow:0 0 15px #00ff88,0 0 25px #6a00ff;font-size:3rem;margin-bottom:10px;}
.hero p{font-size:1.2rem;color:#ccc;}
.filter-section{padding:20px;text-align:center;}
.filter-section input, .filter-section select{padding:8px;margin:0 5px;border-radius:5px;border:none;outline:none;}
.products{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:20px;padding:20px;}
.product{background:#1a1a1a;border-radius:10px;padding:20px;text-align:center;box-shadow:0 0 15px rgba(106,0,255,0.3);transition:transform 0.3s ease,box-shadow 0.3s ease;}
.product:hover{transform:translateY(-5px);box-shadow:0 0 25px rgba(0,255,136,0.5);}
.product img{width:100%;border-radius:8px;margin-bottom:15px;}
.product h3{color:#00ff88;margin-bottom:10px;}
.product p{color:#ccc;font-size:0.9rem;}
.product button{margin-top:10px;padding:10px 20px;background:linear-gradient(90deg,#6a00ff,#00ff88);border:none;border-radius:5px;color:white;font-weight:bold;cursor:pointer;transition:background 0.3s ease;}
.product button:hover{background:linear-gradient(90deg,#00ff88,#6a00ff);}
.cart-sidebar{position:fixed;top:0;left:-350px;width:350px;height:100%;background:#111;box-shadow:2px 0 15px rgba(0,255,136,0.4);overflow-y:auto;transition:left 0.4s ease;padding:20px;z-index:1000;}
.cart-sidebar.active{left:0;}
.cart-sidebar h2{color:#6a00ff;text-shadow:0 0 10px #00ff88;margin-bottom:20px;text-align:center;}
.cart-item{display:flex;align-items:center;margin-bottom:15px;border-bottom:1px solid #333;padding-bottom:10px;}
.cart-item img{width:60px;height:60px;border-radius:5px;margin-left:10px;}
.cart-item div{flex:1;}
.cart-item h4{margin:0;color:#00ff88;}
.cart-item p{margin:5px 0 0;font-size:0.9rem;color:#aaa;}
.remove-btn{background:red;border:none;color:white;padding:5px 8px;border-radius:4px;cursor:pointer;font-size:0.8rem;}
.remove-btn:hover{background:darkred;}
.cart-total{margin-top:20px;font-weight:bold;text-align:center;color:#fff;font-size:1.1rem;}
.checkout-btn{display:block;text-align:center;background:#00ff88;color:#111;padding:12px;margin-top:15px;border-radius:5px;cursor:pointer;font-weight:bold;transition:background 0.3s ease;}
.checkout-btn:hover{background:#6a00ff;color:#fff;}
.close-btn{display:block;text-align:center;background:#6a00ff;color:white;padding:10px;margin-top:15px;border-radius:5px;cursor:pointer;transition:background 0.3s ease;}
.close-btn:hover{background:#00ff88;}
.checkout-form{display:none;margin-top:20px;background:#1a1a1a;padding:15px;border-radius:8px;}
.checkout-form input{width:100%;padding:10px;margin:8px 0;border:none;border-radius:5px;background:#2a2a2a;color:white;}
.checkout-form button{width:100%;padding:10px;background:linear-gradient(90deg,#6a00ff,#00ff88);border:none;border-radius:5px;color:white;font-weight:bold;cursor:pointer;}
.

مهمات, [9/5/2025 1:35 AM]
language-switch{position:absolute;top:20px;right:20px;background:#111;padding:8px 15px;border-radius:8px;cursor:pointer;box-shadow:0 0 10px #6a00ff;color:#00ff88;}
.language-switch:hover{box-shadow:0 0 20px #00ff88;}
footer{background:#111;color:#888;text-align:center;padding:20px;margin-top:40px;font-size:0.9rem;}
</style>
</head>
<body>

<header>
  ⚡ <span id="site-title">أسامة فون</span> ⚡
  <div class="cart" onclick="toggleCart()">🛒 <span id="cartText">السلة</span>: <span id="cartCount">0</span></div>
  <div class="language-switch" onclick="toggleLanguage()">EN/AR</div>
</header>

<section class="hero">
  <h1 id="hero-title">مرحباً بك في أسامة فون</h1>
  <p id="hero-text">أفضل متجر إلكتروني لبيع الهواتف والإكسسوارات بتصميم عصري مستوحى من عالم الـGaming.</p>
</section>

<section class="filter-section">
  <input type="text" id="searchInput" placeholder="ابحث عن منتج..." onkeyup="filterProducts()">
  <select id="categoryFilter" onchange="filterProducts()">
    <option value="all">الكل</option>
    <option value="phone">هواتف</option>
    <option value="earbuds">سماعات</option>
    <option value="accessory">إكسسوارات</option>
  </select>
  <select id="sortFilter" onchange="filterProducts()">
    <option value="default">ترتيب افتراضي</option>
    <option value="price-asc">السعر: من الأقل للأعلى</option>
    <option value="price-desc">السعر: من الأعلى للأقل</option>
    <option value="bestseller">الأكثر مبيعاً</option>
  </select>
</section>

<section class="products" id="productsContainer"></section>

<div id="cartSidebar" class="cart-sidebar">
  <h2 id="cart-title">🛒 السلة</h2>
  <div id="cartItems"></div>
  <div class="cart-total" id="cartTotal">المجموع: 0 $</div>
  <div class="checkout-btn" onclick="toggleCheckout()">إتمام الطلب</div>
  <form id="checkoutForm" class="checkout-form" onsubmit="submitOrder(event)">
    <input type="text" placeholder="الاسم الكامل" required>
    <input type="text" placeholder="العنوان" required>
    <input type="tel" placeholder="رقم الهاتف" required>
    <button type="submit">تأكيد الطلب</button>
  </form>
  <div class="close-btn" onclick="toggleCart()">إغلاق</div>
</div>

<footer>
  <p id="footer-text">© 2025 أسامة فون - جميع الحقوق محفوظة</p>
  <p id="footer-contact">روابط السوشيال ميديا ومعلومات التواصل ستضاف هنا لاحقاً.</p>
</footer>

<script>
// المنتجات
const products = [
  {id:1,nameAR:'هاتف ذكي',nameEN:'Smart Phone',price:299,category:'phone',bestseller:true,img:'https://via.placeholder.com/250x200.png?text=هاتف+1'},
  {id:2,nameAR:'سماعات لاسلكية',nameEN:'Wireless Earbuds',price:59,category:'earbuds',bestseller:true,img:'https://via.placeholder.com/250x200.png?text=سماعات'},
  {id:3,nameAR:'إكسسوار',nameEN:'Accessory',price:19,category:'accessory',bestseller:false,img:'https://via.placeholder.com/250x200.png?text=اكسسوار'},
  {id:4,nameAR:'هاتف متقدم',nameEN:'Advanced Phone',price:499,category:'phone',bestseller:false,img:'https://via.placeholder.com/250x200.png?text=هاتف+2'},
  {id:5,nameAR:'سماعة مميزة',nameEN:'Premium Earbuds',price:89,category:'earbuds',bestseller:false,img:'https://via.placeholder.com/250x200.png?text=سماعة+2'},
  {id:6,nameAR:'إكسسوار فاخر',nameEN:'Luxury Accessory',price:39,category:'accessory',bestseller:true,img:'https://via.placeholder.com/250x200.png?text=اكسسوار+2'}
];

let cart=[];
let lang='ar';

function renderProducts(){
  const container = document.getElementById('productsContainer');
  container.innerHTML='';
  products.forEach(p=>{
    const div = document.createElement('div');
    div.className='product';
    div.dataset.category=p.category;
    div.dataset.price=p.price;
    div.dataset.bestseller=p.bestseller;
    div.innerHTML=`<img src="${p.img}" alt="${p.nameAR}">
      <h3>${lang==='ar'?p.nameAR:p.nameEN}</h3>
      <p>${p.price} $</p>
      <button onclick="addToCart('${lang==='ar'?p.nameAR:p.nameEN}',${p.price},'${p.img}')">${lang==='ar'?'أضف إلى السلة':'Add to Cart'}</button>`;
    container.appendChild(div);
  });
}

function filterProducts(){
  const search = document.getElementById('searchInput').value.toLowerCase();

مهمات, [9/5/2025 1:35 AM]
const category = document.getElementById('categoryFilter').value;
  const sort = document.getElementById('sortFilter').value;
  let filtered = products.filter(p=>{
    const name = lang==='ar'?p.nameAR.toLowerCase():p.nameEN.toLowerCase();
    return name.includes(search) && (category==='all'?true:p.category===category);
  });
  if(sort==='price-asc') filtered.sort((a,b)=>a.price-b.price);
  if(sort==='price-desc') filtered.sort((a,b)=>b.price-a.price);
  if(sort==='bestseller') filtered.sort((a,b)=>b.bestseller-b.bestseller);
  const container = document.getElementById('productsContainer');
  container.innerHTML='';
  filtered.forEach(p=>{
    const div = document.createElement('div');
    div.className='product';
    div.innerHTML=`<img src="${p.img}" alt="${p.nameAR}">
      <h3>${lang==='ar'?p.nameAR:p.nameEN}</h3>
      <p>${p.price} $</p>
      <button onclick="addToCart('${lang==='ar'?p.nameAR:p.nameEN}',${p.price},'${p.img}')">${lang==='ar'?'أضف إلى السلة':'Add to Cart'}</button>`;
    container.appendChild(div);
  });
}

function addToCart(name,price,img){cart.push({name,price,img});updateCartUI();}
function removeFromCart(index){cart.splice(index,1);updateCartUI();}
function updateCartUI(){
  document.getElementById('cartCount').innerText=cart.length;
  const cartItems=document.getElementById('cartItems');
  const cartTotal=document.getElementById('cartTotal');
  cartItems.innerHTML='';
  let total=0;
  cart.forEach((item,index)=>{
    total+=item.price;
    cartItems.innerHTML+=`<div class="cart-item">
      <img src="${item.img}" alt="${item.name}">
      <div><h4>${item.name}</h4><p>${item.price} $</p></div>
      <button class="remove-btn" onclick="removeFromCart(${index})">✖</button>
    </div>`;
  });
  cartTotal.innerText=(lang==='ar'?"المجموع: ":"Total: ")+total+" $";
}

function toggleCart(){document.getElementById('cartSidebar').classList.toggle('active');}
function toggleCheckout(){const form=document.getElementById('checkoutForm');form.style.display=form.style.display==='block'?'none':'block';}

function submitOrder(e){
  e.preventDefault();
  const name = document.getElementById('checkoutForm').querySelectorAll('input')[0].value;
  const address = document.getElementById('checkoutForm').querySelectorAll('input')[1].value;
  const phone = document.getElementById('checkoutForm').querySelectorAll('input')[2].value;
  let total = 0;
  cart.forEach(item=>total+=item.price);

  fetch("YOUR_WEB_APP_URL_HERE", { // ضع رابط Google Apps Script هنا
    method: "POST",
    body: JSON.stringify({name,address,phone,items:cart,total}),
  })
  .then(res=>res.json())
  .then(data=>{
    if(data.status==='success'){
      alert(lang==='ar'?"✅ تم استلام طلبك، سنتواصل معك قريباً!":"✅ Order received! We will contact you soon.");
      document.getElementById('checkoutForm').reset();
      document.getElementById('checkoutForm').style.display='none';
      cart=[];updateCartUI();toggleCart();
    } else {alert("Error: Could not send order.");}
  })
  .catch(err=>alert("Error: "+err));
}

function toggleLanguage(){
  lang=lang==='ar'?'en':'ar';
  document.getElementById('site-title').innerText=lang==='ar'?'أسامة فون':'Osama Phone';
  document.getElementById('hero-title').innerText=lang==='ar'?'مرحباً بك في أسامة فون':'Welcome to Osama Phone';
  document.getElementById('hero-text').innerText=lang==='ar'?'أفضل متجر إلكتروني لبيع الهواتف والإكسسوارات بتصميم عصري مستوحى من عالم الـGaming.':'Best online store for phones and accessories with a modern Gaming-style design.';
  document.getElementById('cart-title').innerText=lang==='ar'?'🛒 السلة':'🛒 Cart';
  document.getElementById('cartText').innerText=lang==='ar'?'السلة':'Cart';
  document.getElementById('checkoutForm').querySelectorAll('input')[0].placeholder=lang==='ar'?'الاسم الكامل':'Full Name';
  document.getElementById('checkoutForm').querySelectorAll('input')[1].placeholder=lang==='ar'?'العنوان':'Address';
  document.getElementById('checkoutForm').querySelectorAll('input')[2].placeholder=lang==='ar'?'رقم الهاتف':'Phone';
  document.getElementById('checkoutForm').

مهمات, [9/5/2025 1:35 AM]
querySelector('button').innerText=lang==='ar'?'تأكيد الطلب':'Submit Order';
  document.getElementById('footer-text').innerText=lang==='ar'?'© 2025 أسامة فون - جميع الحقوق محفوظة':'© 2025 Osama Phone - All Rights Reserved';
  document.getElementById('footer-contact').innerText=lang==='ar'?'روابط السوشيال ميديا ومعلومات التواصل ستضاف هنا لاحقاً.':'Social media links and contact info will be added later.';
  renderProducts();
}

renderProducts();
</script>

</body>
</html>
