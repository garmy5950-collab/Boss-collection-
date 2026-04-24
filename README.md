<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Boss Collection</title>

<style>
body {
  margin: 0;
  font-family: Arial;
  background: #f5f5f5;
}

header {
  background: black;
  color: white;
  text-align: center;
  padding: 15px;
  font-size: 22px;
  letter-spacing: 2px;
}

.products {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px,1fr));
  gap: 15px;
  padding: 15px;
}

.card {
  background: white;
  border-radius: 10px;
  padding: 10px;
  text-align: center;
  box-shadow: 0 3px 10px rgba(0,0,0,0.1);
}

.card img {
  width: 100%;
  border-radius: 8px;
}

button {
  background: black;
  color: white;
  border: none;
  padding: 10px;
  margin-top: 8px;
  width: 100%;
  cursor: pointer;
}

select {
  width: 100%;
  padding: 8px;
  margin-top: 5px;
}

.cart-btn {
  position: fixed;
  bottom: 15px;
  right: 15px;
  background: black;
  color: white;
  padding: 12px;
  border-radius: 50%;
  cursor: pointer;
}

#checkout {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.7);
}

.checkout-box {
  background: white;
  margin: 50px auto;
  padding: 20px;
  width: 90%;
  max-width: 400px;
  border-radius: 10px;
}

input, textarea {
  width: 100%;
  padding: 8px;
  margin-top: 8px;
}

</style>
</head>

<body>

<header>BOSS COLLECTION</header>

<div class="products">

<div class="card">
<img src="https://via.placeholder.com/300">
<h3>Classic Heels</h3>
<p>PKR 2500</p>

<select id="size1">
<option>Size 36</option>
<option>Size 37</option>
<option>Size 38</option>
<option>Size 39</option>
<option>Size 40</option>
</select>

<button onclick="addToCart('Classic Heels','2500','size1')">Add to Cart</button>
</div>

<div class="card">
<img src="https://via.placeholder.com/300">
<h3>Stylish Sandal</h3>
<p>PKR 2200</p>

<select id="size2">
<option>Size 36</option>
<option>Size 37</option>
<option>Size 38</option>
<option>Size 39</option>
<option>Size 40</option>
</select>

<button onclick="addToCart('Stylish Sandal','2200','size2')">Add to Cart</button>
</div>

</div>

<div class="cart-btn" onclick="openCheckout()">🛒</div>

<div id="checkout">
<div class="checkout-box">

<h3>Checkout</h3>

<input type="text" id="name" placeholder="Your Name">
<input type="text" id="phone" placeholder="Phone Number">
<textarea id="address" placeholder="Address"></textarea>

<select id="payment">
<option>Cash on Delivery</option>
<option>Online Payment (JazzCash / Easypaisa)</option>
</select>

<button onclick="placeOrder()">Place Order</button>
<button onclick="closeCheckout()">Cancel</button>

</div>
</div>

<script>
let cart = [];

function addToCart(name, price, sizeId) {
  let size = document.getElementById(sizeId).value;
  cart.push(name + " (" + size + ") - PKR " + price);
  alert("Added to cart");
}

function openCheckout() {
  document.getElementById("checkout").style.display = "block";
}

function closeCheckout() {
  document.getElementById("checkout").style.display = "none";
}

function placeOrder() {
  let name = document.getElementById("name").value;
  let phone = document.getElementById("phone").value;
  let address = document.getElementById("address").value;
  let payment = document.getElementById("payment").value;

  let message = "Order from Boss Collection:%0A";
  message += cart.join("%0A") + "%0A%0A";
  message += "Name: " + name + "%0A";
  message += "Phone: " + phone + "%0A";
  message += "Address: " + address + "%0A";
  message += "Payment: " + payment;

  window.location.href = "https://wa.me/923XXXXXXXXX?text=" + message;
}
</script>

</body>
</html>
