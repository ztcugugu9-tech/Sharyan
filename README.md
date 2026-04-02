<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>متجر الملابس</title>

<style>
body {
    font-family: Arial;
    margin: 0;
    background: #f5f5f5;
}

/* الهيدر */
header {
    background: #111;
    color: white;
    padding: 15px;
    text-align: center;
    font-size: 24px;
}

/* المنتجات */
.products {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px,1fr));
    gap: 20px;
    padding: 20px;
}

.product {
    background: white;
    padding: 15px;
    border-radius: 10px;
    text-align: center;
}

.product img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}

button {
    background: black;
    color: white;
    padding: 10px;
    border: none;
    cursor: pointer;
    margin-top: 10px;
}

/* السلة */
.cart {
    position: fixed;
    top: 10px;
    right: 10px;
    background: white;
    padding: 15px;
    border-radius: 10px;
    width: 200px;
}
</style>
</head>

<body>

<header>
🛍️ متجر الملابس
</header>

<div class="cart">
<h3>السلة</h3>
<ul id="cart-items"></ul>
<p>المجموع: $<span id="total">0</span></p>
</div>

<div class="products">

<div class="product">
<img src="https://via.placeholder.com/200">
<h3>تيشيرت أسود</h3>
<p>$20</p>
<button onclick="addToCart('تيشيرت',20)">أضف للسلة</button>
</div>

<div class="product">
<img src="https://via.placeholder.com/200">
<h3>بنطال جينز</h3>
<p>$35</p>
<button onclick="addToCart('جينز',35)">أضف للسلة</button>
</div>

<div class="product">
<img src="https://via.placeholder.com/200">
<h3>جاكيت</h3>
<p>$50</p>
<button onclick="addToCart('جاكيت',50)">أضف للسلة</button>
</div>

</div>

<script>
let total = 0;

function addToCart(name, price) {
    let list = document.getElementById("cart-items");
    let item = document.createElement("li");
    item.textContent = name + " - $" + price;
    list.appendChild(item);

    total += price;
    document.getElementById("total").textContent = total;
}
</script>

</body>
</html>
