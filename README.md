!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Blue Door Homes</title>

<style>
body {
  font-family: 'Poppins', Arial, sans-serif;
  margin: 0;
  background: #f4f6f9;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #0f172a;
  color: white;
  padding: 15px 30px;
}

.logo {
  font-weight: bold;
  font-size: 20px;
}

nav a {
  color: white;
  margin-left: 15px;
  text-decoration: none;
}

.hero {
  background: url('https://images.unsplash.com/photo-1560185127-6ed189bf02f4');
  background-size: cover;
  color: white;
  text-align: center;
  padding: 90px 20px;
}

.section {
  padding: 40px 20px;
  max-width: 1100px;
  margin: auto;
}

input {
  padding: 10px;
  width: 100%;
  margin-bottom: 20px;
}

.properties {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}

.card {
  background: white;
  border-radius: 10px;
  overflow: hidden;
  cursor: pointer;
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
}

.card img {
  width: 100%;
  height: 180px;
  object-fit: cover;
}

.card-content {
  padding: 15px;
}

.price {
  color: #2563eb;
  font-weight: bold;
}

/* Modal */
.modal {
  display: none;
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.6);
}

.modal-content {
  background: white;
  margin: 10% auto;
  padding: 20px;
  width: 80%;
  max-width: 500px;
}

/* WhatsApp */
.whatsapp {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background: #25D366;
  color: white;
  padding: 15px;
  border-radius: 50%;
  text-decoration: none;
}
</style>
</head>

<body>

<header>
  <div class="logo">🏠 Blue Door Homes</div>
  <nav>
    <a href="#">Home</a>
    <a href="#">Properties</a>
    <a href="#">Contact</a>
  </nav>
</header>

<section class="hero">
  <h1>Find Your Perfect Home</h1>
  <p>Buy, rent, or invest in Johannesburg</p>
</section>

<section class="section">
  <h2>Search Properties</h2>
  <input type="text" id="search" placeholder="Search location..." onkeyup="filterProperties()">

  <div class="properties" id="propertyList">

    <div class="card" onclick="openModal('Sandton Apartment','R950,000','Modern apartment in Sandton')">
      <img src="https://images.unsplash.com/photo-1600585154340-be6161a56a0c">
      <div class="card-content">
        <h3>Sandton Apartment</h3>
        <p class="price">R950,000</p>
      </div>
    </div>

    <div class="card" onclick="openModal('Soweto House','R1,200,000','Family home in Soweto')">
      <img src="https://images.unsplash.com/photo-1570129477492-45c003edd2be">
      <div class="card-content">
        <h3>Soweto House</h3>
        <p class="price">R1,200,000</p>
      </div>
    </div>

    <div class="card" onclick="openModal('Randburg Flat','R650,000','Starter apartment in Randburg')">
      <img src="https://images.unsplash.com/photo-1599423300746-b62533397364">
      <div class="card-content">
        <h3>Randburg Flat</h3>
        <p class="price">R650,000</p>
      </div>
    </div>

  </div>
</section>

<!-- Modal -->
<div id="modal" class="modal" onclick="closeModal()">
  <div class="modal-content">
    <h2 id="title"></h2>
    <p id="price"></p>
    <p id="desc"></p>
  </div>
</div>

<section class="section">
  <h2>Contact</h2>
  <p>Phone: +27 11 000 0000</p>
  <p>Email: info@bluedoorhomes.co.za</p>
</section>

<!-- WhatsApp -->
<a class="whatsapp" href="https://wa.me/27700000000" target="_blank">💬</a>

<script>
function filterProperties() {
  let input = document.getElementById("search").value.toLowerCase();
  let cards = document.querySelectorAll(".card");

  cards.forEach(card => {
    let text = card.innerText.toLowerCase();
    card.style.display = text.includes(input) ? "block" : "none";
  });
}

function openModal(title, price, desc) {
  document.getElementById("modal").style.display = "block";
  document.getElementById("title").innerText = title;
  document.getElementById("price").innerText = price;
  document.getElementById("desc").innerText = desc;
}

function closeModal() {
  document.getElementById("modal").style.display = "none";
}
</script>

</body>
</html>
