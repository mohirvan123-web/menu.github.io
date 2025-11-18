<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Thawing Reminder - Alarm Agresif & Persistent (MLGJAK)</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    
    <style>
        /* ==================== 
           CSS: REVISI STYLING & RESPONSIVITAS 
           ==================== */
        :root {
            --color-white: #ffffff;
            --color-light-bg: #f7f9ff; /* Background sangat pucat */
            --color-primary-blue: #4A90E2; /* Biru Primer */
            --color-accent-pink: #FF69B4; /* Hot Pink */
            --color-text-dark: #333333;
            --color-warning: #FFC0CB; /* Soft Pink untuk warning */
            --color-alert: #DC3545; /* Merah untuk alarm */
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--color-light-bg);
            min-height: 100vh;
            margin: 0; 
            padding: 20px 10px;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            transition: background-color 0.2s; 
            color: var(--color-text-dark);
        }

        .main-container {
            background-color: var(--color-white);
            padding: 30px;
            border-radius: 16px; /* Lebih modern */
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08); /* Shadow yang halus */
            text-align: center;
            width: 100%;
            max-width: 850px; /* Lebar lebih besar untuk 2 kolom */
            box-sizing: border-box; 
        }

        h1 {
            color: var(--color-primary-blue);
            font-weight: 700;
            margin-bottom: 5px;
        }

        p {
            color: #666;
            margin-bottom: 25px;
            font-size: 0.9em;
        }

        .timer-list {
            /* Tampilan 2 Kolom Default (untuk tablet ke atas) */
            display: grid;
            grid-template-columns: repeat(2, 1fr); 
            gap: 20px;
            margin-top: 20px;
        }

        .timer-card {
            border: 1px solid #e0e0e0;
            padding: 20px;
            border-radius: 12px;
            background-color: var(--color-white);
            transition: all 0.3s;
            text-align: center; /* Konten di tengah */
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
        }

        .timer-card h2 {
            color: var(--color-accent-pink); /* Nama item pakai Pink */
            padding-bottom: 5px;
            font-size: 1.3em;
            font-weight: 600;
        }

        .countdown-display {
            font-size: 2.5em; /* Lebih besar */
            margin: 15px 0;
            padding: 10px 0;
            font-weight: 700;
            color: var(--color-primary-blue);
            background: none; /* Hilangkan background default */
        }

        .alarm-message {
            color: var(--color-alert);
            font-weight: 600;
            margin-top: 10px;
            font-size: 0.95em;
        }

        .timer-controls {
            display: flex;
            gap: 10px;
            margin-top: 15px;
            align-items: center;
            justify-content: center;
        }

        .timer-controls label {
            font-weight: 400;
            white-space: nowrap;
        }
        
        .timer-controls input {
            padding: 10px 5px;
            max-width: 60px; 
            text-align: center; 
            border: 1px solid #ddd;
            border-radius: 8px;
            font-family: 'Poppins', sans-serif;
            font-size: 1em;
        }

        .timer-controls button {
            padding: 10px 15px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            flex-grow: 1; 
            transition: background-color 0.2s, transform 0.1s;
        }
        .timer-controls button:active { transform: scale(0.98); }

        .start-btn { 
            background-color: var(--color-primary-blue); 
            color: white; 
        }
        .start-btn:hover { background-color: #387ad1; }
        
        .reset-btn { 
            background-color: var(--color-alert); /* Reset pakai warna merah/pink */
            color: white; 
        }
        .reset-btn:hover { background-color: #b82c3c; }

        /* --- STATE ALERT CSS --- */

        /* WARNING (15 Menit) - Menggunakan Soft Pink dan Biru Tua */
        .timer-card.warning {
            border-color: var(--color-warning);
            box-shadow: 0 0 10px rgba(255, 192, 203, 0.5);
            background-color: #fffafa;
        }
        .timer-card.warning .countdown-display {
            color: var(--color-primary-blue); 
            animation: pulse-warn 1s infinite alternate; 
        }
        .timer-card.warning h2 { color: var(--color-primary-blue); }

        /* ALERT (Waktu Habis) - Menggunakan Hot Pink Agresif */
        .timer-card.alert {
            border-color: var(--color-alert);
            background-color: #ffeff3;
            box-shadow: 0 0 10px rgba(255, 105, 180, 0.7);
        }
        .timer-card.alert .countdown-display {
            color: var(--color-alert); 
            font-size: 2.2em;
            animation: none;
        }
        
        /* ALARM GLOBAL AGRESIF (Flash Body) */
        .flash-alarm-red {
            background-color: #ff4d6d !important; /* Pink Agresif */
            transition: background-color 0.2s; 
        }

        /* ANIMASI */
        @keyframes pulse-warn {
            from { transform: scale(1); opacity: 1; }
            to { transform: scale(1.01); opacity: 0.9; }
        }

        /* MEDIA QUERY - OPTIMALISASI MOBILE & TABLET */
        
        /* Tablet/Small Desktop - Pertahankan 2 kolom */
        @media (min-width: 651px) and (max-width: 850px) {
            .main-container { padding: 20px; }
        }

        /* Mobile View - Paksakan 1 kolom */
        @media (max-width: 650px) {
            body { padding: 10px 0; }
            .main-container { padding: 15px; border-radius: 0; box-shadow: none; max-width: 100%;}
            
            /* Ubah ke 1 kolom */
            .timer-list { 
                grid-template-columns: 1fr; 
                gap: 15px; 
            } 
            
            .timer-card { padding: 15px; }
            h1 { font-size: 1.8em; }
            p { font-size: 0.8em; }
            
            .timer-card h2 { font-size: 1.2em; }
            .countdown-display { font-size: 2em; margin: 10px 0; }
            
            /* Kontrol: Input dan Tombol berbaris vertikal */
            .timer-controls { 
                flex-wrap: wrap; 
                gap: 8px; 
                justify-content: space-between;
            }
            
            .timer-controls label { 
                flex-basis: 100%; /* Label ambil 1 baris */
                text-align: left;
                font-size: 0.9em;
            }
            .timer-controls input { 
                max-width: 80px; 
                flex-grow: 0;
            }
            /* Tombol START/RESET bagi rata 50% */
            .timer-controls button { 
                padding: 10px; 
                font-size: 0.9em; 
                flex-basis: calc(50% - 5px); 
            }
        }
    </style>
    
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-database.js"></script>
</head>
<body>
    <div class="main-container">
        <h1>Timer Thawing Reminder 🧊 (SHARED)</h1>
        <p>Status timer disinkronkan secara real-time. UI Modern: Biru & Pink.</p>
        
        <div class="timer-list" id="timer-list">
            </div>
    </div>

    <script>
       // ===================================
        // FIREBASE CONFIGURATION (Biarkan tidak berubah)
        // ===================================
        const firebaseConfig = {
          apiKey: "AIzaSyBtUlghTw806GuGuwOXGNgoqN6Rkcg0IMM",
          authDomain: "thawing-ec583.firebaseapp.com",
          databaseURL: "https://thawing-ec583-default-rtdb.asia-southeast1.firebasedatabase.app",
          projectId: "thawing-ec583",
          storageBucket: "thawing-ec583.firebasestorage.app", 
          messagingSenderId: "1043079332713",
          appId: "1:1043079332713:web:6d289ad2b7c13a222bb3f8",
          measurementId: "G-WLBFJ6V7QT"            
        };


        // Initialize Firebase
        try {
            firebase.initializeApp(firebaseConfig);
        } catch (e) {
            console.error("Firebase Initialization Failed. Check your config.", e);
        }
        
        // Dapatkan referensi database
        const dbRef = firebase.database().ref('thawingTimers');
        
        /* ==================== 
           JAVASCRIPT LOGIC (Hampir tidak berubah, hanya penyesuaian kelas CSS)
           ==================== */
        
        // --- KONFIGURASI APLIKASI ---
        const THAWING_ITEMS = [
            { id: 1, name: "ADONAN", defaultTimeMinutes: 40 },
            { id: 2, name: "ACIN", defaultTimeMinutes: 60 },
            { id: 3, name: "MIE", defaultTimeMinutes: 120 },
            { id: 4, name: "PENTOL", defaultTimeMinutes: 120 },
            { id: 5, name: "SURAI NAGA", defaultTimeMinutes: 120 },
            { id: 6, name: "KRUPUK MIE", defaultTimeMinutes: 120 },
            { id: 7, name: "KULIT PANGSIT", defaultTimeMinutes: 120 },
        ];
        
        const WARNING_TIME_SECONDS = 15 * 60; // 15 menit

        // --- VARIABEL GLOBAL ALARM AGRESIF ---
        let activeIntervals = {}; 
        let audioCtx;
        let notificationPermission = Notification.permission;
        
        let titleInterval = null;
        let flashInterval = null;
        const originalTitle = document.title;
        const WARNING_TITLE_PREFIX = '🚨 HABIS! - ';
        const FLASH_COLOR_CLASS = 'flash-alarm-red'; 

        // Fungsi Format Waktu
        function formatTime(totalSeconds) {
            const hours = Math.floor(totalSeconds / 3600);
            const minutes = Math.floor((totalSeconds % 3600) / 60);
            const seconds = totalSeconds % 60;

            const h = String(hours).padStart(2, '0');
            const m = String(minutes).padStart(2, '0');
            const s = String(seconds).padStart(2, '0');

            return `${h}:${m}:${s}`;
        }
        
        function resumeAudioContext() {
             // Dibiarkan untuk kompatibilitas
             if (audioCtx && audioCtx.state === 'suspended') {
                 audioCtx.resume().catch(e => console.error("Failed to resume AudioContext:", e));
             }
        }
        
        // =================================================
        // 🚨 FUNGSI TEXT-TO-SPEECH
        // =================================================
        function speakMessage(message) {
            if ('speechSynthesis' in window) {
                // Hentikan ucapan yang sedang berjalan
                window.speechSynthesis.cancel(); 
                
                const utterance = new SpeechSynthesisUtterance(message);
                
                const voices = window.speechSynthesis.getVoices();
                const indoVoice = voices.find(v => v.lang === 'id-ID' || v.lang === 'id_ID');
                
                if (indoVoice) {
                    utterance.voice = indoVoice;
                } else {
                    utterance.lang = 'id-ID'; // Fallback
                }
                
                utterance.rate = 1.0; 
                utterance.volume = 1.0; 
                
                window.speechSynthesis.speak(utterance);
            } else {
                console.warn("Web Speech API tidak didukung. Alarm ucapan dinonaktifkan.");
            }
        }
        // =================================================


        function sendNotification(itemName) {
            if (notificationPermission === 'granted') {
                new Notification("⏰ WAKTU THAWING HABIS!", {
                    body: `🚨 Segera ambil bahan: ${itemName}.`,
                    tag: 'thawing-alarm',
                    renotify: true, 
                    requireInteraction: true 
                }).onclick = function() {
                    window.focus(); 
                    this.close();
                    stopAggressiveAlarm(); 
                };
            }
        }

        function startVibrationAlert() {
            if ('vibrate' in navigator) {
                const pattern = [1000, 500, 1000]; 
                navigator.vibrate(pattern);
            }
        }

        function startFlashAlarm() {
            if (flashInterval) return;
            let isFlashing = false;
            flashInterval = setInterval(() => {
                isFlashing = !isFlashing;
                document.body.classList.toggle(FLASH_COLOR_CLASS, isFlashing);
            }, 200);
        }

        function startTitleAlert(itemName) {
            if (titleInterval) return;
            let isAlertState = false;
            titleInterval = setInterval(() => {
                isAlertState = !isAlertState;
                document.title = isAlertState 
                    ? WARNING_TITLE_PREFIX + itemName 
                    : originalTitle;
            }, 800);
        }

        function stopAggressiveAlarm() {
            if (titleInterval) {
                clearInterval(titleInterval);
                titleInterval = null;
            }
            if (flashInterval) {
                clearInterval(flashInterval);
                flashInterval = null;
            }
            document.title = originalTitle;
            document.body.classList.remove(FLASH_COLOR_CLASS);
            // Hentikan suara ucapan
            if ('speechSynthesis' in window) {
                window.speechSynthesis.cancel(); 
            }
        }
        
        // --- LOGIKA UTAMA: FUNGSI TICK ---
        
        /**
         * Fungsi tick sekarang dipicu oleh listener Firebase.
         */
        function tick(itemId, endTimeMs, inputMinutes) {
            const timerCard = document.getElementById(`card-${itemId}`);
            if (!timerCard) return;

            const display = document.getElementById(`display-${itemId}`);
            const alarmMessage = document.getElementById(`msg-${itemId}`);
            // Gunakan find() untuk mendapatkan item yang benar, karena innerHTML h2 bisa berubah
            const item = THAWING_ITEMS.find(i => i.id === itemId);
            const itemName = item ? item.name : 'Bahan';
            
            clearTimeout(activeIntervals[itemId]);

            const now = Date.now();
            let duration = Math.floor((endTimeMs - now) / 1000); 
            
            // Perbarui UI Kontrol
            const inputTime = document.getElementById(`time-input-${itemId}`);
            const startButton = document.getElementById(`start-btn-${itemId}`);
            const resetButton = document.getElementById(`reset-btn-${itemId}`);
            if (inputTime) inputTime.value = inputMinutes; 
            if (inputTime) inputTime.readOnly = true;
            if (startButton) startButton.style.display = 'none';
            if (resetButton) resetButton.style.display = 'block';

            // 1. Update tampilan
            if (duration >= 0) {
                 display.textContent = formatTime(duration);
            }
           
            // 2. Transisi ke mode WARNING (15 Menit)
            if (duration <= WARNING_TIME_SECONDS && duration > 0) {
                if (!timerCard.classList.contains('warning')) {
                    timerCard.classList.add('warning');
                    timerCard.classList.remove('alert'); 
                    const remainingMinutes = Math.ceil(duration / 60);
                    alarmMessage.textContent = `🔔 PERINGATAN! ${itemName} tersisa ${remainingMinutes} menit.`;
                    alarmMessage.style.display = 'block';
                }
            } else if (duration > WARNING_TIME_SECONDS) {
                 timerCard.classList.remove('warning');
                 alarmMessage.style.display = 'none';
            }

            // 3. Bunyikan alarm di mode WARNING (setiap 30 detik)
            if (duration <= WARNING_TIME_SECONDS && duration > 0 && duration % 30 === 0) {
                const remainingMinutes = Math.ceil(duration / 60);
                // 🚨 TTS: Peringatan 15 Menit
                speakMessage(`Perhatian! Waktu thawing ${itemName} kurang ${remainingMinutes} menit.`); 
            }
            
            // 4. Kondisi Waktu Habis: (Alarm & Hapus dari database)
            if (duration <= 0) {
                // Hentikan interval lokal
                clearTimeout(activeIntervals[itemId]);
                delete activeIntervals[itemId];
                
                // Hapus entry dari Firebase
                dbRef.child(itemId).remove().catch(e => console.log('Hapus item gagal.'));
                
                display.textContent = "WAKTU HABIS!";
                timerCard.classList.remove('warning');
                timerCard.classList.add('alert'); 
                alarmMessage.textContent = `✅ SELESAI! Bahan ${itemName} butuh penanganan.`;
                alarmMessage.style.display = 'block';
                
                // --- AKTIVASI ALARM AGRESIF (Lokal di perangkat ini) ---
                sendNotification(itemName);
                startVibrationAlert(); 
                startTitleAlert(itemName);
                startFlashAlarm();
                
                // 🚨 TTS: Waktu Habis
                speakMessage(`PERINGATAN KERAS! Waktu thawing ${itemName} telah habis! Segera ambil bahan!`); 
                
                return; 
            }
            
            // 5. Jadwalkan tick berikutnya (Lokal)
            activeIntervals[itemId] = setTimeout(() => tick(itemId, endTimeMs, inputMinutes), 1000);
        }

        // --- FUNGSI PUBLIK (Dipanggil oleh User) ---
        
        // FUNGSI INI MENGIRIM PERUBAHAN KE FIREBASE
        function startCountdown(itemId) {
            resumeAudioContext(); 
            Notification.requestPermission().then(permission => {
                notificationPermission = permission; 
            });
            
            const timerCard = document.getElementById(`card-${itemId}`);
            const inputTime = document.getElementById(`time-input-${itemId}`);
            const durationMinutes = parseInt(inputTime.value);

            if (isNaN(durationMinutes) || durationMinutes <= 0) {
                alert(`Mohon masukkan waktu thawing yang valid.`);
                return;
            }
            
            const durationMs = durationMinutes * 60 * 1000;
            const endTimeMs = Date.now() + durationMs; 
            
            // 🚨 LOGIKA UTAMA: TULIS KE DATABASE 
            dbRef.child(itemId).set({ 
                endTime: endTimeMs, 
                inputMinutes: durationMinutes 
            })
            .then(() => {
                console.log(`Timer ${itemId} started and synced.`);
            })
            .catch(error => {
                alert("Gagal memulai timer. Periksa koneksi atau aturan Firebase.");
                console.error(error);
            });
        }

        // FUNGSI INI MENGHAPUS DATA DARI FIREBASE
        function resetTimer(itemId) {
            stopAggressiveAlarm(); 
            
            // 🚨 LOGIKA UTAMA: HAPUS DARI DATABASE
            dbRef.child(itemId).remove()
            .then(() => {
                console.log(`Timer ${itemId} reset and synced.`);
            })
            .catch(error => {
                alert("Gagal mereset timer. Periksa koneksi atau aturan Firebase.");
                console.error(error);
            });
            
            // UI akan direset secara lokal oleh listener Firebase
            localResetUI(itemId);
        }

        // Mereset UI lokal berdasarkan item default
        function localResetUI(itemId, inputMinutes = null) {
            const item = THAWING_ITEMS.find(i => i.id === itemId);
            if (!item) return;

            const finalInput = inputMinutes !== null ? inputMinutes : item.defaultTimeMinutes;
            
            clearTimeout(activeIntervals[itemId]);
            delete activeIntervals[itemId];

            const timerCard = document.getElementById(`card-${itemId}`);
            const inputTime = document.getElementById(`time-input-${itemId}`);
            const display = document.getElementById(`display-${itemId}`);
            const alarmMessage = document.getElementById(`msg-${itemId}`);
            const startButton = document.getElementById(`start-btn-${itemId}`);
            const resetButton = document.getElementById(`reset-btn-${itemId}`);
            
            if (!timerCard || !inputTime || !display || !startButton || !resetButton) return; 

            timerCard.classList.remove('alert', 'warning');
            inputTime.readOnly = false;
            startButton.style.display = 'block';
            resetButton.style.display = 'none';
            alarmMessage.style.display = 'none';

            inputTime.value = finalInput;
            display.textContent = formatTime(finalInput * 60);

            // Fokus pada input hanya jika di-reset
            // inputTime.focus(); 
        }

        // Fungsi untuk membuat elemen HTML timer
        function createTimerCard(item) {
            const timerListContainer = document.getElementById('timer-list');
            
            const card = document.createElement('div');
            card.className = 'timer-card';
            card.id = `card-${item.id}`;
            
            card.innerHTML = `
                <h2>${item.name}</h2>
                <div id="display-${item.id}" class="countdown-display">
                    ${formatTime(item.defaultTimeMinutes * 60)}
                </div>
                
                <div id="msg-${item.id}" class="alarm-message" style="display: none;"></div>

                <div class="timer-controls">
                    <label for="time-input-${item.id}">Durasi (mnt):</label>
                    <input type="number" id="time-input-${item.id}" value="${item.defaultTimeMinutes}" min="1" max="180">
                    <button id="start-btn-${item.id}" class="start-btn">START</button>
                    <button id="reset-btn-${item.id}" class="reset-btn" style="display: none;">RESET</button>
                </div>
            `;
            
            timerListContainer.appendChild(card);
            
            document.getElementById(`start-btn-${item.id}`).addEventListener('click', () => startCountdown(item.id));
            document.getElementById(`reset-btn-${item.id}`).addEventListener('click', () => resetTimer(item.id));

            document.getElementById(`time-input-${item.id}`).addEventListener('input', (event) => {
                if (!document.getElementById(`time-input-${item.id}`).readOnly) {
                    const minutes = parseInt(event.target.value) || 0;
                    const display = document.getElementById(`display-${item.id}`);
                    display.textContent = formatTime(minutes * 60);
                }
            });
            
            localResetUI(item.id, item.defaultTimeMinutes);
        }

        // ===================================
        // 🚨 LOGIKA SINKRONISASI REAL-TIME
        // ===================================
        
        document.addEventListener('DOMContentLoaded', () => {
            // 1. Render semua kartu timer
            THAWING_ITEMS.forEach(item => {
                createTimerCard(item);
            });
            notificationPermission = Notification.permission;
            
            // 2. Pasang Listener Real-time
            dbRef.on('value', (snapshot) => {
                const timersData = snapshot.val() || {}; 

                THAWING_ITEMS.forEach(item => {
                    const itemId = item.id;
                    const timerState = timersData[itemId];
                    
                    if (timerState && timerState.endTime) {
                        const endTime = timerState.endTime;
                        const inputMinutes = timerState.inputMinutes || item.defaultTimeMinutes;
                        
                        if (endTime < Date.now()) {
                            // Waktu sudah habis (past event), panggil tick untuk trigger alarm/reset
                            tick(itemId, endTime, inputMinutes); 
                        } else {
                            // Waktu masih berjalan
                            tick(itemId, endTime, inputMinutes);
                        }
                    } else {
                        // Timer TIDAK berjalan (Sudah di-reset atau belum dimulai)
                        clearTimeout(activeIntervals[itemId]);
                        delete activeIntervals[itemId];

                        localResetUI(itemId, item.defaultTimeMinutes); 
                    }
                });
            });
        });
    </script>
</body>
</html>
