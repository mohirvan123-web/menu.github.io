<!DOCTYPE html>
<html lang="id" style="scroll-behavior: smooth;">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Selamat Datang di Gacoan</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 min-h-screen flex flex-col font-sans">

  <header class="bg-red-600 text-white p-4 shadow-lg sticky top-0 z-50">
    <div class="container mx-auto flex justify-between items-center">
      <h1 class="text-2xl font-bold tracking-wide">Gacoan Jakarta</h1>
      <a href="#cart-section" class="md:hidden">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.102 1.743.707 1.743H18a2 2 0 002-2V7.786" />
        </svg>
      </a>
    </div>
  </header>

  <nav class="bg-white sticky top-16 z-40 shadow-sm md:shadow-md p-4">
    <div class="container mx-auto">
      <ul class="flex justify-around items-center space-x-4 overflow-x-auto whitespace-nowrap md:justify-center">
        <li><a href="#noodle-section" class="text-gray-800 font-semibold px-4 py-2 rounded-full hover:bg-gray-200 transition-colors">🍜 Noodle</a></li>
        <li><a href="#dimsum-section" class="text-gray-800 font-semibold px-4 py-2 rounded-full hover:bg-gray-200 transition-colors">🥟 Dimsum</a></li>
        <li><a href="#bar-section" class="text-gray-800 font-semibold px-4 py-2 rounded-full hover:bg-gray-200 transition-colors">🥤 Beverage</a></li>
      </ul>
    </div>
  </nav>

  <main class="flex-1 container mx-auto p-6 flex flex-col md:flex-row gap-8">

    <section class="flex-1">
      <h2 class="text-3xl font-bold mb-6 text-gray-800 border-b-2 border-red-500 pb-2">SELAMAT DATAG DI GACOAN .....</h2>

      <h3 id="noodle-section" class="text-2xl font-bold mb-4 mt-8 text-gray-700">🍜 Noodle</h3>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Suit</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Gacoan Lv.0</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie gacoan Lv. 1</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Gacoan Lv. 2</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Gacoan Lv. 3</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Gacoan Lv. 4</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Gacoan Lv. 6</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Gacoan Lv. 8</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Hompimpa Lv. 1</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
         <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Hompimpa Lv. 2</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
         <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Hompimpa Lv. 3</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
         <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Hompimpa Lv. 4</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Hompimpa Lv. 6</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 12.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div><div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Mie Hompimpa Lv. 8</h4>
          <p class="text-yellow-500 text-sm font-semibold">NOODLE</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 12.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-sm hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
      </div>
      
      

      <h3 id="dimsum-section" class="text-2xl font-bold mb-4 mt-8 text-gray-700">🥟 Dimsum</h3>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Udang Keju</h4>
          <p class="text-blue-600 text-sm font-semibold">DIMSUM.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Udang Rambutan</h4>
          <p class="text-blue-600 text-sm font-semibold">DIMSUM.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Lumpia Udang</h4>
          <p class="text-blue-600 text-sm font-semibold">DIMSUM.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Siomay Ayam</h4>
          <p class="text-blue-600 text-sm font-semibold">DIMSUM.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
          <h4 class="font-bold text-lg text-gray-900 mt-2">Pangsit Goreng</h4>
          <p class="text-blue-600 text-sm font-semibold">DIMSUM.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 11.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-1 px-2 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
      </div>

      <h3 id="bar-section" class="text-2xl font-bold mb-4 mt-8 text-gray-700">🥤 Beverage</h3>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Es Gobak Sodor</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Es Petak Umpet</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Es Teklek</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Es Sluku Bathok</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        </div>

      <h3 id="bar-section" class="text-2xl font-bold mb-4 mt-8 text-gray-700">🥤 Beverage</h3>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Green Thai Tea</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Thai Tea</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Lemon Tea</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Tea</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Coklat</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Vanilla Late</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Teh Tarik</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
        <div class="bg-white rounded-2xl shadow-lg p-4 flex flex-col transform transition-transform duration-300 hover:scale-[1.02]">
           <h4 class="font-bold text-lg text-gray-900 mt-2">Air Mineral</h4>
          <p class="text-gray-600 text-sm font-semibold">BAR.</p>
          <p class="font-bold text-lg mt-2 text-red-600">Rp 10.000</p>
          <button class="add-to-cart mt-auto bg-red-600 text-white rounded-full py-2 px-4 font-semibold hover:bg-red-700 transition-colors duration-300">Tambah</button>
        </div>
      </div>
    </section>

    <aside id="cart-section" class="bg-white rounded-2xl shadow-lg p-6 flex flex-col sticky top-24 h-fit md:w-1/3 lg:w-1/4">
      <h2 class="text-xl font-bold mb-4 text-gray-800">🛒 Keranjang Belanja</h2>
      <ul id="cart" class="space-y-4 text-sm text-gray-700">
        <li class="text-gray-400 italic text-center py-4">Keranjang Anda kosong</li>
      </ul>
      <div class="border-t-2 border-gray-200 mt-6 pt-6 flex justify-between items-center font-bold text-lg">
        <span>Total:</span>
        <span id="total" class="text-green-600">Rp 0</span>
      </div>
      <div class="mt-6">
        <label class="block text-sm font-semibold mb-2">Nama Pelanggan:</label>
        <input id="customerName" type="text" placeholder="Masukkan nama Anda" class="w-full border border-gray-300 rounded-lg p-3 focus:outline-none focus:border-red-500 transition-colors" />
      </div>
      <div class="mt-4">
        <label class="block text-sm font-semibold mb-2">Pilih Tipe Pesanan:</label>
        <select id="orderType" class="w-full border border-gray-300 rounded-lg p-3 focus:outline-none focus:border-red-500 transition-colors">
          <option value="Dine In">Dine In</option>
          <option value="Take Away">Take Away</option>
        </select>
      </div>
      <button id="checkout" class="w-full mt-6 bg-green-600 text-white rounded-lg py-3 font-semibold hover:bg-green-700 transition-colors duration-300 shadow-md">Checkout via WhatsApp</button>
    </aside>

  </main>

  <footer class="bg-gray-200 text-center p-4 text-sm text-gray-600 mt-8">
    © 2025 Pilih Menu Online
  </footer>

  <script>
    const cart = document.getElementById("cart");
    const totalEl = document.getElementById("total");
    const checkoutBtn = document.getElementById("checkout");
    const orderType = document.getElementById("orderType");
    const customerName = document.getElementById("customerName");
    const addButtons = document.querySelectorAll(".add-to-cart");

    let totalHarga = 0;

    function updateTotalDisplay() {
      totalEl.innerText = "Rp " + totalHarga.toLocaleString("id-ID");
    }

    function ensureEmptyTextRemoved() {
      if (cart.children.length === 1 && cart.children[0].classList.contains("text-gray-400")) {
        cart.innerHTML = "";
      }
    }

    function tambahKeKeranjang(item, harga) {
      ensureEmptyTextRemoved();

      let existing = [...cart.children].find(li => li.dataset.item === item);
      if (existing) {
        let qtySpan = existing.querySelector(".qty");
        let qty = parseInt(qtySpan.innerText, 10);
        qty++;
        qtySpan.innerText = qty;
        totalHarga += harga;
        updateTotalDisplay();
        return;
      }

      const li = document.createElement("li");
      li.dataset.item = item;
      li.dataset.harga = harga;
      li.classList.add("flex", "justify-between", "items-center", "gap-2");

      li.innerHTML = `
        <span class="text-sm">${item}</span>
        <div class="flex items-center gap-2">
          <button class="minus bg-gray-200 px-2 rounded">-</button>
          <span class="qty px-2">1</span>
          <button class="plus bg-gray-200 px-2 rounded">+</button>
          <span class="harga text-sm">Rp ${harga.toLocaleString("id-ID")}</span>
          <button class="hapus text-red-500 hover:text-red-700">❌</button>
        </div>
      `;

      li.querySelector(".plus").addEventListener("click", () => {
        let qtySpan = li.querySelector(".qty");
        let qty = parseInt(qtySpan.innerText, 10);
        qty++;
        qtySpan.innerText = qty;
        totalHarga += harga;
        updateTotalDisplay();
      });

      li.querySelector(".minus").addEventListener("click", () => {
        let qtySpan = li.querySelector(".qty");
        let qty = parseInt(qtySpan.innerText, 10);
        if (qty > 1) {
          qty--;
          qtySpan.innerText = qty;
          totalHarga -= harga;
          updateTotalDisplay();
        }
      });

      li.querySelector(".hapus").addEventListener("click", () => {
        let qty = parseInt(li.querySelector(".qty").innerText, 10);
        totalHarga -= harga * qty;
        if (totalHarga < 0) totalHarga = 0;
        li.remove();
        updateTotalDisplay();

        if (cart.children.length === 0) {
          cart.innerHTML = `<li class="text-gray-400 italic text-center py-4">Keranjang Anda kosong</li>`;
        }
      });

      cart.appendChild(li);
      totalHarga += harga;
      updateTotalDisplay();
    }

    addButtons.forEach(btn => {
      btn.addEventListener("click", () => {
        const card = btn.closest(".flex.flex-col");
        const item = card.querySelector("h4").innerText.trim();
        const hargaText = card.querySelector("p.font-bold").innerText;
        const harga = parseInt(hargaText.replace(/[^\d]/g, ""), 10);
        tambahKeKeranjang(item, harga);
      });
    });

    checkoutBtn.addEventListener("click", () => {
      if (cart.children.length === 1 && cart.children[0].classList.contains("text-gray-400")) {
        alert("Keranjang masih kosong!");
        return;
      }

      const nama = customerName.value.trim();
      if (!nama) {
        alert("Silakan isi Nama Pelanggan terlebih dahulu.");
        customerName.focus();
        return;
      }

      let pesan = `Halo, saya mau pesan.%0A`;
      pesan += `Nama: ${nama}%0A%0A`;
      pesan += `Daftar pesanan:%0A`;

      [...cart.children].forEach(li => {
        const item = li.dataset.item;
        const hargaPerItem = Number(li.dataset.harga);
        const qty = Number(li.querySelector(".qty").innerText);
        const subtotal = hargaPerItem * qty;
        pesan += `- ${item} x${qty} = Rp ${subtotal.toLocaleString("id-ID")}%0A`;
      });

      pesan += `%0ATotal: ${totalEl.innerText}%0A`;
      pesan += `Tipe Pesanan: ${orderType.value}%0A%0A`;
      pesan += `Terima kasih 🙏`;

      const noWA = "628991190404";
      const url = `https://api.whatsapp.com/send?phone=${noWA}&text=${pesan}`;

      window.open(url, "_blank", "noopener,noreferrer");
    });
  </script>

</body>
</html>
