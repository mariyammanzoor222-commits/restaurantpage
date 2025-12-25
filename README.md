# restaurantpage
<section class="hero">
    <div class="hero-content">
        <h1>FRESH HOT & <br><span>MADE TO LOVE.</span></h1>
        <p>Premium Beef Burger - $12.00</p>
        <button class="btn-main" onclick="addToCart('Classic Beef Burger', 12.00)">ADD TO CART</button>
    </div>
    <div class="hero-image">
        <img src="https://images.unsplash.com/photo-1568901346375-23c9450c58cd?q=80&w=1000&auto=format&fit=crop" alt="Burger">
    </div>
</section>

<div id="cartSidebar" class="cart-sidebar">
    <div class="cart-header">
        <h2>Your Order</h2>
        <button onclick="toggleCart()">×</button>
    </div>
    <div id="cartBody" class="cart-body">
        <p id="emptyMessage">Your cart is empty!</p>
        <ul id="itemList" style="list-style: none; padding: 0;"></ul>
    </div>
    <div class="cart-footer">
        <h3 style="margin-bottom: 10px;">Total: $<span id="cartTotal">0.00</span></h3>
        <button class="btn-checkout" onclick="alert('Proceeding to Payment...')">CHECKOUT NOW</button>
    </div>
</div>
<script>
    let total = 0;
    const cartItems = [];

    function toggleCart() {
        document.getElementById('cartSidebar').classList.toggle('active');
    }

    function addToCart(name, price) {
        // 1. Add price to total
        total += price;
        document.getElementById('cartTotal').innerText = total.toFixed(2);

        // 2. Add item name to the list
        const list = document.getElementById('itemList');
        const emptyMsg = document.getElementById('emptyMessage');
        
        if (emptyMsg) emptyMsg.style.display = 'none';

        const li = document.createElement('li');
        li.style.borderBottom = "1px solid #eee";
        li.style.padding = "10px 0";
        li.innerHTML = `<strong>${name}</strong> - $${price.toFixed(2)}`;
        list.appendChild(li);

        // 3. Open the cart so the user sees it happened
        document.getElementById('cartSidebar').classList.add('active');
    }
</script>
