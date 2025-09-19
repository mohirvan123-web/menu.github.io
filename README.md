<!DOCTYPE html>
<html lang="id" style="scroll-behavior: smooth;">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Reservasi Online Gacoan</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .form-input {
            width: 100%;
            border: 1px solid #d1d5db;
            border-radius: 0.5rem;
            padding: 0.75rem;
            transition-property: border-color;
            transition-duration: 300ms;
        }

        .form-input:focus {
            outline: none;
            border-color: #3b82f6;
        }
        
        @keyframes popIn {
          0% { transform: scale(0); opacity: 0; }
          80% { transform: scale(1.1); opacity: 1; }
          100% { transform: scale(1); }
        }

        .qty-btn {
          animation: popIn 0.2s ease-out;
        }
        
        .modal {
            display: none;
            position: fixed;
            z-index: 100;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.6);
            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);
        }

        .modal-content {
            background-color: #fefefe;
            margin: 10vh auto;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            width: 90%;
            max-width: 500px;
            position: relative;
            transform: translateY(-50px);
            opacity: 0;
            animation: fadeInTop 0.5s forwards;
        }

        @keyframes fadeInTop {
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }
        
        .close-btn {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
            transition: color 0.2s;
        }

        .close-btn:hover,
        .close-btn:focus {
            color: #000;
            text-decoration: none;
            cursor: pointer;
        }
        
        .sticky-buttons {
            position: sticky;
            bottom: 0;
            z-index: 50;
            padding: 1rem;
            background-color: white;
            box-shadow: 0 -2px 10px rgba(0,0,0,0.1);
            display: flex;
            justify-content: center;
        }

        /* Responsive grid for menu */
        .menu-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1.5rem;
        }
        
        @media (min-width: 768px) {
            .menu-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }
    </style>
</head>
<body class="bg-gray-100 min-h-screen flex flex-col font-sans">
    
    <header class="bg-blue-600 rounded-xl text-white p-1 shadow-lg sticky top-0 z-50">
        <div class="container mx-auto flex justify-between items-center">
            <h1 class="text-xl font-bold tracking-wide">Gacoan Jakarta</h1>
        </div>
    </header>

    <nav class="bg-white sticky top-10 z-40 shadow-sm md:shadow-md p-2">
        <div class="container mx-auto">
            <ul class="flex justify-around items-center space-x-4 overflow-x-auto whitespace-nowrap md:justify-center">
                <li><a href="#noodle-section" class="text-gray-800 font-semibold px-4 py-2 rounded-full hover:bg-gray-200 transition-colors duration-200">🍜 Noodle</a></li>
                <li><a href="#dimsum-section" class="text-gray-800 font-semibold px-4 py-2 rounded-full hover:bg-gray-200 transition-colors duration-200">🥟 Dimsum</a></li>
                <li><a href="#beverage-section" class="text-gray-800 font-semibold px-4 py-2 rounded-full hover:bg-gray-200 transition-colors duration-200">🥤 Beverage</a></li>
            </ul>
        </div>
    </nav>

    <main class="flex-1 container mx-auto p-4 flex flex-col gap-8">
        <section class="flex-1">
            <h2 class="text-3xl font-bold mb-3 text-gray-800 border-b-2 border-pink-500 pb-2">FORMULIR RESERVASI ONLINE</h2>

            <div class="bg-white rounded-xl shadow-md p-6 mb-8 border-t-4 border-blue-600">
                <form id="reservation-form" class="space-y-4">
                    <div>
                        <label for="customerName" class="block text-sm font-semibold mb-2">Nama Pelanggan:</label>
                        <input type="text" id="customerName" placeholder="Masukkan nama Anda" class="form-input focus:border-blue-500 transition-colors" required />
                    </div>
                    <div>
                        <label for="customerPhone" class="block text-sm font-semibold mb-2">Nomor HP:</label>
                        <input type="tel" id="customerPhone" placeholder="Contoh: 081234567890" class="form-input focus:border-blue-500 transition-colors" required />
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <label for="reservationDate" class="block text-sm font-semibold mb-2">Tanggal Reservasi:</label>
                            <input type="date" id="reservationDate" class="form-input focus:border-blue-500 transition-colors" required />
                        </div>
                        <div>
                            <label for="reservationTime" class="block text-sm font-semibold mb-2">Jam Reservasi:</label>
                            <input type="time" id="reservationTime" class="form-input focus:border-blue-500 transition-colors" required />
                        </div>
                    </div>
                    <div>
                        <label class="block text-sm font-semibold mb-2">Metode Pembayaran:</label>
                        <select id="paymentMethod" class="form-input focus:border-blue-500 transition-colors" required>
                            <option value="Langsung di Kasir">Langsung di Kasir</option>
                            <option value="Transfer ke Rekening 13579">Transfer ke Rekening 13579</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-sm font-semibold mb-2">Tipe Pesanan:</label>
                        <select id="orderType" class="form-input focus:border-blue-500 transition-colors" required>
                            <option value="Dine In">Dine In</option>
                            <option value="Take Away">Take Away</option>
                        </select>
                    </div>
                </form>
            </div>

            <h3 id="noodle-section" class="text-2xl font-bold mb-4 mt-8 text-gray-700 border-b-2 border-pink-500 pb-0">🍜 Noodle</h3>
            <div id="noodle-list" class="menu-grid">
                </div>

            <h3 id="dimsum-section" class="text-2xl font-bold mb-4 mt-8 text-gray-700 border-b-2 border-pink-500 pb-0">🥟 Dimsum</h3>
            <div id="dimsum-list" class="menu-grid">
                </div>

            <h3 id="beverage-section" class="text-2xl font-bold mb-4 mt-8 text-gray-700 border-b-2 border-pink-500 pb-0">🥤 Beverage</h3>
            <div id="beverage-list" class="menu-grid">
                </div>

        </section>
    </main>
    
    <div class="sticky-buttons">
        <div class="container mx-auto flex justify-center">
            <button id="viewOrderList" class="w-full max-w-sm bg-blue-600 text-white rounded-lg py-1 px-6 font-semibold hover:bg-blue-700 transition-colors duration-300 shadow-md">Lihat Pesanan</button>
        </div>
    </div>

    <div id="orderModal" class="modal">
        <div class="modal-content">
            <span class="close-btn">&times;</span>
            <h3 class="text-xl font-bold mb-4 text-gray-800">Daftar Pesanan Anda</h3>
            <div id="modalOrderList" class="space-y-4">
                </div>
            <div class="mt-6 pt-4 border-t border-gray-300 flex justify-between items-center">
                <span id="modalTotal" class="text-lg font-bold text-gray-800">Total: Rp 0</span>
                <button id="modalSubmitBtn" class="bg-blue-600 text-white rounded-lg py-2 px-4 font-semibold hover:bg-blue-700 transition-colors duration-300 transform active:scale-95">Submit Reservasi via WhatsApp</button>
            </div>
        </div>
    </div>

    <footer class="bg-gray-200 text-center p-4 text-sm text-gray-600 mt-8">
        © 2025 Reservasi Online Gacoan
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const menuData = [
                { name: "Mie Suit", category: "NOODLE", price: 11000, type: "pink" },
                { name: "Mie Gacoan Lv.0", category: "NOODLE", price: 11000, type: "yellow" },
                { name: "Mie gacoan Lv. 1", category: "NOODLE", price: 11000, type: "yellow" },
                { name: "Mie Gacoan Lv. 2", category: "NOODLE", price: 11000, type: "yellow" },
                { name: "Mie Gacoan Lv. 3", category: "NOODLE", price: 11000, type: "yellow" },
                { name: "Mie Gacoan Lv. 4", category: "NOODLE", price: 11000, type: "yellow" },
                { name: "Mie Gacoan Lv. 6", category: "NOODLE", price: 12000, type: "yellow" },
                { name: "Mie Gacoan Lv. 8", category: "NOODLE", price: 12000, type: "yellow" },
                { name: "Mie Hompimpa Lv.1", category: "NOODLE", price: 11000, type: "blue" },
                { name: "Mie Hompimpa Lv.2", category: "NOODLE", price: 11000, type: "blue" },
                { name: "Mie Hompimpa Lv. 3", category: "NOODLE", price: 11000, type: "blue" },
                { name: "Mie Hompimpa Lv. 4", category: "NOODLE", price: 11000, type: "blue" },
                { name: "Mie Hompimpa Lv. 6", category: "NOODLE", price: 12000, type: "blue" },
                { name: "Mie Hompimpa Lv. 8", category: "NOODLE", price: 12000, type: "blue" },

                { name: "Udang Keju", category: "DIMSUM", price: 10000, type: "pink" },
                { name: "Udang Rambutan", category: "DIMSUM", price: 10000, type: "pink" },
                { name: "Lumpia Udang", category: "DIMSUM", price: 10000, type: "pink" },
                { name: "Siomay Ayam", category: "DIMSUM", price: 10000, type: "pink" },
                { name: "Pangsit Goreng", category: "DIMSUM", price: 11000, type: "pink" },

                { name: "Es Gobak Sodor", category: "BEVERAGE", price: 10000, type: "blue" },
                { name: "Es Petak Umpet", category: "BEVERAGE", price: 10000, type: "blue" },
                { name: "Es Teklek", category: "BEVERAGE", price: 10000, type: "blue" },
                { name: "Es Sluku Bathok", category: "BEVERAGE", price: 10000, type: "blue" },
                { name: "Green Thai Tea", category: "BEVERAGE", price: 10000, type: "blue" },
                { name: "Thai Tea", category: "BEVERAGE", price: 10000, type: "blue" },
                { name: "Lemon Tea", category: "BEVERAGE", price: 10000, type: "blue" },
                { name: "Tea", category: "BEVERAGE", price: 10000, type: "blue" },
                { name: "Coklat", category: "BEVERAGE", price: 10000, type: "blue" },
                { name: "Vanilla Late", category: "BEVERAGE", price: 10000, type: "blue" },
                { name: "Teh Tarik", category: "BEVERAGE", price: 10000, type: "blue" },
                { name: "Air Mineral", category: "BEVERAGE", price: 5000, type: "blue" },
            ];

            const noodleListEl = document.getElementById('noodle-list');
            const dimsumListEl = document.getElementById('dimsum-list');
            const beverageListEl = document.getElementById('beverage-list');
            const viewOrderBtn = document.getElementById('viewOrderList');
            const modal = document.getElementById('orderModal');
            const modalOrderList = document.getElementById('modalOrderList');
            const modalTotal = document.getElementById('modalTotal');
            const modalSubmitBtn = document.getElementById('modalSubmitBtn');
            const closeModalBtn = document.querySelector('.close-btn');

            const selectedMenus = {};

            function renderMenu() {
                menuData.forEach(item => {
                    const card = document.createElement('div');
                    card.classList.add('bg-white', 'rounded-2xl', 'shadow-lg', 'p-4', 'flex', 'flex-col', 'transform', 'transition-transform', 'duration-300', 'hover:scale-[1.02]');
                    
                    const categoryColor = item.type === "pink" ? "text-pink-600" : (item.type === "yellow" ? "text-yellow-500" : "text-blue-400");
                    
                    card.innerHTML = `
                        <h4 class="font-bold text-lg text-gray-900 mt-2">${item.name}</h4>
                        <p class="${categoryColor} text-sm font-semibold">${item.category}</p>
                        <p class="font-bold text-lg mt-1 text-pink-600">Rp ${item.price.toLocaleString("id-ID")}</p>
                        <div class="flex items-center gap-2 mt-auto pt-2">
                            <button class="minus-qty bg-gray-200 px-2 rounded transform transition-transform duration-150 active:scale-95">-</button>
                            <span class="qty-display px-2 w-8 text-center">0</span>
                            <button class="plus-qty bg-gray-200 px-2 rounded transform transition-transform duration-150 active:scale-95">+</button>
                        </div>
                    `;

                    const minusBtn = card.querySelector('.minus-qty');
                    const plusBtn = card.querySelector('.plus-qty');
                    const qtyDisplay = card.querySelector('.qty-display');

                    plusBtn.addEventListener('click', () => {
                        let qty = (selectedMenus[item.name] || 0) + 1;
                        selectedMenus[item.name] = qty;
                        qtyDisplay.innerText = qty;
                    });

                    minusBtn.addEventListener('click', () => {
                        let qty = (selectedMenus[item.name] || 0) - 1;
                        if (qty < 0) qty = 0;
                        selectedMenus[item.name] = qty;
                        qtyDisplay.innerText = qty;
                    });

                    if (item.category === "NOODLE") {
                        noodleListEl.appendChild(card);
                    } else if (item.category === "DIMSUM") {
                        dimsumListEl.appendChild(card);
                    } else if (item.category === "BEVERAGE") {
                        beverageListEl.appendChild(card);
                    }
                });
            }

            renderMenu();

            function generateOrderMessage() {
                const customerName = document.getElementById('customerName').value.trim();
                const customerPhone = document.getElementById('customerPhone').value.trim();
                const reservationDate = document.getElementById('reservationDate').value;
                const reservationTime = document.getElementById('reservationTime').value;
                const paymentMethod = document.getElementById('paymentMethod').value;
                const orderType = document.getElementById('orderType').value;

                let totalHarga = 0;
                const selectedItems = [];

                for (const name in selectedMenus) {
                    if (selectedMenus[name] > 0) {
                        const itemData = menuData.find(m => m.name === name);
                        if (itemData) {
                            selectedItems.push({
                                name: name,
                                qty: selectedMenus[name],
                                price: itemData.price,
                            });
                            totalHarga += selectedMenus[name] * itemData.price;
                        }
                    }
                }
                
                let pesan = `🔔 *Reservasi Baru* 🔔%0A%0A`;
                pesan += `👤 *Nama:* ${customerName}%0A`;
                pesan += `📞 *Nomor HP:* ${customerPhone}%0A`;
                pesan += `🗓️ *Tanggal:* ${reservationDate}%0A`;
                pesan += `⏰ *Jam:* ${reservationTime}%0A`;
                pesan += `💳 *Metode Bayar:* ${paymentMethod}%0A`;
                pesan += `📦 *Tipe Pesanan:* ${orderType}%0A%0A`;
                
                pesan += `🍜 *Daftar Menu Pesanan:*%0A`;
                if (selectedItems.length > 0) {
                    selectedItems.forEach(item => {
                        pesan += `- ${item.name}   ➡️   ${item.qty} pcs%0A`;
                    });
                } else {
                    pesan += `- _Tidak ada menu yang dipilih_%0A`;
                }

                pesan += `%0A────────────────────────%0A`;
                pesan += `💸 *Estimasi Total:* Rp ${totalHarga.toLocaleString("id-ID")}%0A`;
                pesan += `────────────────────────%0A%0A`;
                pesan += `*Terima kasih*, reservasi Anda akan segera kami konfirmasi. 🙏`;
                
                return { pesan, selectedItems, totalHarga };
            }

            function validateForm() {
                const customerName = document.getElementById('customerName').value.trim();
                const customerPhone = document.getElementById('customerPhone').value.trim();
                const reservationDate = document.getElementById('reservationDate').value;
                const reservationTime = document.getElementById('reservationTime').value;
                if (!customerName || !customerPhone || !reservationDate || !reservationTime) {
                    alert('Mohon lengkapi semua data reservasi.');
                    return false;
                }
                return true;
            }

            function handleSubmission() {
                if (validateForm()) {
                    const { pesan } = generateOrderMessage();
                    const noWA = "628991190404";
                    const url = `https://api.whatsapp.com/send?phone=${noWA}&text=${pesan}`;
                    window.open(url, '_blank', 'noopener,noreferrer');
                }
            }

            modalSubmitBtn.addEventListener('click', handleSubmission);

            viewOrderBtn.addEventListener('click', () => {
                if (validateForm()) {
                    const { selectedItems, totalHarga } = generateOrderMessage();
                    modalOrderList.innerHTML = '';
                    if (selectedItems.length > 0) {
                        selectedItems.forEach(item => {
                            const itemEl = document.createElement('div');
                            itemEl.classList.add('flex', 'justify-between', 'items-center', 'py-2', 'border-b', 'border-gray-200');
                            itemEl.innerHTML = `
                                <span>${item.qty}x ${item.name}</span>
                                <span>Rp ${(item.qty * item.price).toLocaleString("id-ID")}</span>
                            `;
                            modalOrderList.appendChild(itemEl);
                        });
                    } else {
                        modalOrderList.innerHTML = '<p class="text-gray-500 text-center">Belum ada menu yang dipilih.</p>';
                    }
                    modalTotal.innerText = `Total: Rp ${totalHarga.toLocaleString("id-ID")}`;
                    modal.style.display = 'block';
                }
            });

            closeModalBtn.addEventListener('click', () => {
                modal.style.display = 'none';
            });

            window.addEventListener('click', (event) => {
                if (event.target === modal) {
                    modal.style.display = 'none';
                }
            });
        });
    </script>

</body>
</html>
