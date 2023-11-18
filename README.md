<html>
<head>

    <title>Shopping Cart</title>
   <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
</head>

<body>

    <div class="container-fluid p-5 bg-primary text-white text-center">
     <h1><mark>Bootstrap Framework</mark></h1><br>
     <body>
        <h1>Login</h1>
        <form id="login-form">
        <label>Username</label>
        <input type="text" id="login-user"><br>
        <label>Password</label>
        <input type="text" id="login-pass"><br>
        <button type="submit">Login</button>
        </form>
        <p id='login-status'></p>
        <h1>Register</h1>
        <form id="reg-form">
        <label>Username</label>
        <input type="text" id="reg-user"><br>
        <label>Password</label>
        <input type="text" id="reg-pass"><br>
        <button type="submit">Register</button>
        </form>
        <p id='reg-status'></p>
        <p>Already have an account? <a href="#" onclick="showLogin()">Login here</a></p>
    </div>
    <div class="hidden">
        <h1>Shopping Cart</h1>
        <div class="products">
            <div class="text-bg-dark text-center">
                    <h2>mango</h2>
            <img src="C:\Users\srira\OneDrive\Desktop\akshi\img1.png" width="200px" height="200px">
            <p> mango is very beautiful</p>
            <p>Price: $150</p>
            <button class="add-to-cart" onclick="addToCart('mango', 150)">Add to Cart</button>
            </div>
            <div class="text-bg-info text-center">
                <h2>watermelon</h2>
            <img src="C:\Users\srira\OneDrive\Desktop\akshi\img2.png" width="200px" height="200px">
            <p>the fruit is very beautiful and size <big></big></p>
            <p>Price: $120</p>
            <button class="add-to-cart" onclick="addToCart('watermelon', 500)">Add to Cart</button>
            </div>
            <div class="text-bg-danger text-center">
                <h2>banana</h2>
                <img src="C:\Users\srira\OneDrive\Desktop\akshi\img3.png" width="200px" height="200px">
                <p>energy fruit</p>
                <p>Price: $40</p>
                <button class="add-to-cart" onclick="addToCart('banana',40 )">Add to Cart</button>
            </div>
            <div class="text-bg-secondary text-center">
                <h2>guava</h2>
            <img src="C:\Users\srira\OneDrive\Desktop\akshi\img5.png" width="200px" height="200px">
            <p> fruit is so tasty</p>
            <p>Price: $90</p>
            <button class="add-to-cart" onclick="addToCart('guava',90)">Add to Cart</button>
        </div>
        <div class="text-bg-info text-center">
        <div class="product">
            <h2>sapodila</h2>
            <img src="C:\Users\srira\OneDrive\Desktop\akshi\img4.png"  width="200px" height="200px">
            <p>so sweet</p>
            <p>Price: $60</p>
            <button class="add-to-cart" onclick="addToCart('sapodila', 60)">Add to Cart</button>
        </div>  
    </div>
    <div class="cart">
        <h2>Shopping Cart</h2>
        <ul id="cart-items"></ul>
        <p>Total: $<span id="total">0</span></p>
        <button onclick="checksout()">Checkout</button>
    </div>
</div>
<script>
    const user=[
{username:"user1", password:"pass1"},
{username:"user2", password:"pass2"},
];
document.getElementById('login-form').addEventListener('submit',function(e){e.preventDefault();
const username=document.getElementById('login-user').value;
const password=document.getElementById('login-pass').value;
const users=user.find(u => u.username===username && u.password===password);
if(users)
{
document.getElementById('login-status').textContent='Login Sucessful';
}
else
{
document.getElementById('login-status').textContent='Invaild Credentials!';
}
});
document.getElementById('reg-form').addEventListener('submit',function(e){e.preventDefault();
const regUsername=document.getElementById('reg-user').value;
const regPassword=document.getElementById('reg-pass').value;
if(regUsername==='' || regPassword===''){ document.getElementById('reg-status').textContent="Please fill the both Fields!"
}
else
{
user.push({Username: regUsername,Password:regPassword});
document.getElementById('reg-status').textContent='Registration Successful !'
}
});
let cartItems = [];

function addToCart(product, price) {
cartItems.push({product, price});
updateCart();
}

function updateCart() {
    cartItems.push({product, price});
    updateCart();
}

function updateCart() {
    let cartList = document.getElementById("cart-items");
    let totalElement = document.getElementById("total");
    let total = 0;

    cartList.innerHTML = "";
    cartItems.forEach(item => {
        let listItem = document.createElement("li");
        listItem.innerText = ${item.product} - $${item.price};
        cartList.appendChild(listItem);
        total += item.price;
    });

    totalElement.innerText = total;
}




// Add product and cart logic similar to the previous example

function checksout() {
    alert('Thank you for your purchase!');
}

</script>
</body>

</html>
