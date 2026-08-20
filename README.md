# freshkart
```html
<!DOCTYPE html>
<html lang="mr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>FreshKart Grocery Store</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:Arial, sans-serif;
    background:#f5f7f4;
    color:#17221a;
}

/* NAVBAR */
header{
    background:#ffffff;
    padding:15px 6%;
    display:flex;
    align-items:center;
    gap:20px;
    box-shadow:0 2px 10px rgba(0,0,0,0.08);
    position:sticky;
    top:0;
    z-index:100;
}

.logo{
    font-size:25px;
    font-weight:bold;
    color:#16833d;
    white-space:nowrap;
}

.logo span{
    color:#f3a400;
}

.search{
    flex:1;
    padding:13px 18px;
    border:none;
    background:#f1f3f0;
    border-radius:10px;
    font-size:15px;
    outline:none;
}

.cart{
    background:#16833d;
    color:white;
    border:none;
    padding:12px 18px;
    border-radius:10px;
    font-weight:bold;
    cursor:pointer;
}

/* HERO */
.hero{
    margin:30px auto;
    max-width:1150px;
    padding:55px;
    border-radius:25px;
    background:linear-gradient(110deg,#dff5df,#fff1c9);
    display:flex;
    align-items:center;
    justify-content:space-between;
}

.badge{
    background:white;
    padding:9px 15px;
    border-radius:30px;
    color:#16833d;
    font-weight:bold;
}

.hero h1{
    font-size:48px;
    margin:18px 0;
}

.hero p{
    font-size:18px;
    color:#555;
    max-width:550px;
    line-height:1.6;
}

.hero button{
    margin-top:25px;
    padding:14px 24px;
    border:none;
    border-radius:10px;
    background:#16833d;
    color:white;
    font-size:16px;
    font-weight:bold;
    cursor:pointer;
}

.hero-img{
    font-size:100px;
}

/* SECTION */
section{
    max-width:1150px;
    margin:40px auto;
    padding:0 20px;
}

h2{
    margin-bottom:20px;
}

/* CATEGORIES */
.categories{
    display:grid;
    grid-template-columns:repeat(6,1fr);
    gap:15px;
}

.category{
    background:white;
    padding:20px 10px;
    text-align:center;
    border-radius:15px;
    border:1px solid #eee;
    font-weight:bold;
    cursor:pointer;
    transition:0.2s;
}

.category:hover{
    transform:translateY(-4px);
}

.category div{
    font-size:40px;
    margin-bottom:8px;
}

/* PRODUCTS */
.products{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:20px;
}

.product{
    background:white;
    padding:18px;
    border-radius:18px;
    border:1px solid #eee;
    transition:0.2s;
}

.product:hover{
    transform:translateY(-5px);
    box-shadow:0 8px 20px rgba(0,0,0,0.08);
}

.product-img{
    height:150px;
    background:#f3f6f1;
    border-radius:14px;
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:75px;
}

.product h3{
    margin-top:15px;
}

.product p{
    color:#777;
    margin-top:5px;
}

.price{
    font-size:20px;
    font-weight:bold;
    margin-top:8px;
}

.add{
    width:100%;
    margin-top:12px;
    padding:11px;
    border:1px solid #16833d;
    background:white;
    color:#16833d;
    border-radius:9px;
    font-weight:bold;
    cursor:pointer;
}

.add:hover{
    background:#16833d;
    color:white;
}

/* FOOTER */
footer{
    margin-top:50px;
    padding:35px 20px;
    text-align:center;
    background:#17221a;
    color:white;
}

/* MOBILE */
@media(max-width:800px){

    header{
        flex-wrap:wrap;
    }

    .search{
        order:3;
        flex-basis:100%;
    }

    .hero{
        margin:15px;
        padding:35px 25px;
    }

    .hero h1{
        font-size:36px;
    }

    .hero-img{
        font-size:60px;
    }

    .categories{
        grid-template-columns:repeat(3,1fr);
    }

    .products{
        grid-template-columns:repeat(2,1fr);
    }
}

@media(max-width:500px){

    .logo{
        font-size:21px;
    }

    .hero{
        flex-direction:column;
        align-items:flex-start;
    }

    .hero-img{
        margin-top:25px;
        align-self:center;
    }

    .categories{
        grid-template-columns:repeat(2,1fr);
    }

    .products{
        grid-template-columns:1fr;
    }
}
</style>
</head>

<body>

<!-- NAVBAR -->
<header>

<div class="logo">
Fresh<span>Kart</span> 🛒
</div>

<input
    class="search"
    id="searchBox"
    type="text"
    placeholder="काय हवे आहे ते शोधा..."
    onkeyup="searchProducts()"
>

<button class="cart" onclick="showCart()">
🛒 Cart (0)
</button>

</header>


<!-- HERO -->
<div class="hero">

<div>

<span class="badge">
आजचं खास ऑफर 🎉
</span>

<h1>
ताजं सामान,<br>
तुमच्या दारात!
</h1>

<p>
फळे, भाज्या, किराणा आणि रोजच्या गरजेच्या वस्तू
एका क्लिकवर. सोपं, जलद आणि विश्वासार्ह.
</p>

<button onclick="goProducts()">
आता खरेदी करा →
</button>

</div>

<div class="hero-img">
🥦🍎🛍️
</div>

</div>


<!-- CATEGORIES -->
<section>

<h2>श्रेणी निवडा</h2>

<div class="categories">

<div class="category">
<div>🥬</div>
भाज्या
</div>

<div class="category">
<div>🍎</div>
फळे
</div>

<div class="category">
<div>🌾</div>
किराणा
</div>

<div class="category">
<div>🥛</div>
डेअरी
</div>

<div class="category">
<div>🍪</div>
स्नॅक्स
</div>

<div class="category">
<div>🧴</div>
घरगुती
</div>

</div>

</section>


<!-- PRODUCTS -->
<section id="products">

<h2>लोकप्रिय उत्पादने</h2>

<div class="products" id="productList">


<div class="product">

<div class="product-img">
🍅
</div>

<h3>ताजे टोमॅटो</h3>

<p>1 kg</p>

<div class="price">
₹40
</div>

<button class="add" onclick="addCart(this)">
+ Add to Cart
</button>

</div>


<div class="product">

<div class="product-img">
🍎
</div>

<h3>Fresh Apples</h3>

<p>1 kg</p>

<div class="price">
₹140
</div>

<button class="add" onclick="addCart(this)">
+ Add to Cart
</button>

</div>


<div class="product">

<div class="product-img">
🥛
</div>

<h3>Amul Milk</h3>

<p>1 L</p>

<div class="price">
₹65
</div>

<button class="add" onclick="addCart(this)">
+ Add to Cart
</button>

</div>


<div class="product">

<div class="product-img">
🍚
</div>

<h3>तांदूळ</h3>

<p>5 kg</p>

<div class="price">
₹320
</div>

<button class="add" onclick="addCart(this)">
+ Add to Cart
</button>

</div>


<div class="product">

<div class="product-img">
🥔
</div>

<h3>बटाटे</h3>

<p>1 kg</p>

<div class="price">
₹35
</div>

<button class="add" onclick="addCart(this)">
+ Add to Cart
</button>

</div>


<div class="product">

<div class="product-img">
🍌
</div>

<h3>केळी</h3>

<p>1 Dozen</p>

<div class="price">
₹60
</div>

<button class="add" onclick="addCart(this)">
+ Add to Cart
</button>

</div>


<div class="product">

<div class="product-img">
🌾
</div>

<h3>गहू</h3>

<p>5 kg</p>

<div class="price">
₹250
</div>

<button class="add" onclick="addCart(this)">
+ Add to Cart
</button>

</div>


<div class="product">

<div class="product-img">
🍪
</div>

<h3>बिस्कीट</h3>

<p>Pack</p>

<div class="price">
₹30
</div>

<button class="add" onclick="addCart(this)">
+ Add to Cart
</button>

</div>

</div>

</section>


<!-- FOOTER -->
<footer>

<strong>FreshKart Grocery Store 🛒</strong>

<br><br>

ताजं • स्वस्त • विश्वासार्ह

<br><br>

© 2026 FreshKart. All Rights Reserved.

</footer>


<script>

let cartCount = 0;

function addCart(button){

    cartCount++;

    document.querySelector(".cart").innerHTML =
    "🛒 Cart (" + cartCount + ")";

    button.innerHTML = "✓ Added";

    button.style.background = "#e5f6e8";

    button.style.color = "#16833d";
}


function goProducts(){

    document.getElementById("products")
    .scrollIntoView({
        behavior:"smooth"
    });

}


function showCart(){

    if(cartCount === 0){

        alert("तुमची Cart सध्या रिकामी आहे 🛒");

    }else{

        alert(
            "तुमच्या Cart मध्ये " +
            cartCount +
            " वस्तू आहेत 🛒"
        );

    }

}


function searchProducts(){

    let input =
    document.getElementById("searchBox")
    .value
    .toLowerCase();

    let products =
    document.querySelectorAll(".product");

    products.forEach(function(product){

        let name =
        product.querySelector("h3")
        .innerText
        .toLowerCase();

        if(name.includes(input)){

            product.style.display = "";

        }else{

            product.style.display = "none";

        }

    });

}

</script>

</body>
</html>
```
