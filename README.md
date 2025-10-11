<script>
    // GANTI IP INI DENGAN ALAMAT IP LOKAL TABLET ANDA!
    const SERVER_IP = '192.168.1.2';
    const WS_URL = `ws://${SERVER_IP}:8080`;
    
    // Inisialisasi WebSocket
    const ws = new WebSocket(WS_URL);

    const tableGrid = document.getElementById('table-grid');
    const modeAdmin1Btn = document.getElementById('mode-admin1');
    const modeAdmin2Btn = document.getElementById('mode-admin2');
    const currentModeDisplay = document.getElementById('current-mode');
    let currentMode = 'admin1'; // Default mode
    
    // Status Meja akan diisi oleh server
    let tableStatus = {}; 

    // --- Penanganan WebSocket ---
    
    // Ketika koneksi berhasil dibuka
    ws.onopen = () => {
        console.log("Terhubung ke server WebSocket.");
    };

    // Ketika menerima pesan dari server
    ws.onmessage = (event) => {
        const message = JSON.parse(event.data);
        if (message.type === 'STATUS_UPDATE') {
            tableStatus = message.data; // Perbarui status
            renderTables(); // Render ulang tampilan
        }
    };

    // Jika terjadi error koneksi
    ws.onerror = (error) => {
        console.error("Kesalahan WebSocket:", error);
        tableGrid.innerHTML = `<div class="col-span-full p-4 bg-yellow-100 text-yellow-800 rounded-lg">KONEKSI GAGAL! Pastikan server Termux berjalan di IP: ${SERVER_IP}.</div>`;
    };

    // --- Fungsi Render dan Toggle ---
    
    function renderTables() {
        tableGrid.innerHTML = '';
        const tableIds = Object.keys(tableStatus); // Ambil semua ID meja dari data server
        
        if (tableIds.length === 0) {
            tableGrid.innerHTML = `<div class="col-span-full p-4 bg-blue-100 text-blue-800 rounded-lg">Menunggu data status meja dari server...</div>`;
            return;
        }

        tableIds.forEach(tableId => {
            const status = tableStatus[tableId];
            
            let bgColor, statusText, clickableClass;

            if (status === 'kosong') {
                bgColor = 'bg-green-500 hover:bg-green-600';
                statusText = 'KOSONG';
                clickableClass = 'cursor-pointer active:scale-95';
            } else {
                bgColor = 'bg-red-500 hover:bg-red-600';
                statusText = 'TERISI';
                clickableClass = 'cursor-pointer active:scale-95';
            }

            if (currentMode === 'admin2') {
                clickableClass = 'cursor-default';
                bgColor = status === 'kosong' ? 'bg-green-500' : 'bg-red-500';
            }

            const tableCard = document.createElement('div');
            tableCard.className = `meja-card p-6 rounded-xl shadow-lg text-white font-bold text-center ${bgColor} ${clickableClass}`;
            tableCard.innerHTML = `
                <p class="text-5xl mb-2">${tableId}</p>
                <p class="text-xl">${statusText}</p>
            `;
            
            if (currentMode === 'admin1') {
                tableCard.addEventListener('click', () => {
                    // Kirim permintaan perubahan status ke server
                    ws.send(JSON.stringify({
                        type: 'TOGGLE_TABLE',
                        tableId: tableId
                    }));
                });
            }
            
            tableGrid.appendChild(tableCard);
        });
    }

    // Fungsi untuk mengubah Mode Aplikasi
    function setMode(mode) {
        currentMode = mode;
        currentModeDisplay.textContent = mode === 'admin1' ? 'Admin 1' : 'Admin 2';
        
        // Perbarui tampilan tombol (omitted for brevity, use your original styling)
        if (mode === 'admin1') {
             modeAdmin1Btn.classList.add('bg-red-700', 'ring-2', 'ring-red-300');
             modeAdmin2Btn.classList.remove('bg-blue-700', 'ring-2', 'ring-blue-300');
        } else {
             modeAdmin2Btn.classList.add('bg-blue-700', 'ring-2', 'ring-blue-300');
             modeAdmin1Btn.classList.remove('bg-red-700', 'ring-2', 'ring-red-300');
        }
        
        renderTables();
    }

    // Event Listeners untuk tombol Mode
    modeAdmin1Btn.addEventListener('click', () => setMode('admin1'));
    modeAdmin2Btn.addEventListener('click', () => setMode('admin2'));

    // Inisialisasi tampilan
    setMode('admin1');
</script>
