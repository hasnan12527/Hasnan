<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Unbenned Akun WhatsApp V1</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #1a1a1a, #2d2d2d);
            color: #fff;
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Login Page */
        .login-container {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(10px);
        }

        .login-box {
            background: rgba(255, 255, 255, 0.05);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            text-align: center;
            max-width: 400px;
            width: 90%;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .skull {
            font-size: 80px;
            margin-bottom: 20px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        .login-box h1 {
            margin-bottom: 30px;
            color: #ff6b6b;
            font-size: 24px;
        }

        .input-group {
            margin-bottom: 20px;
            text-align: left;
        }

        .input-group label {
            display: block;
            margin-bottom: 5px;
            color: #ccc;
            font-size: 14px;
        }

        .input-group input {
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.1);
            color: #fff;
            font-size: 16px;
            transition: all 0.3s;
        }

        .input-group input:focus {
            outline: none;
            background: rgba(255, 255, 255, 0.2);
            box-shadow: 0 0 10px rgba(255, 107, 107, 0.5);
        }

        .login-btn {
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 8px;
            background: linear-gradient(135deg, #ff6b6b, #ee5a24);
            color: #fff;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 20px;
        }

        .login-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 107, 107, 0.4);
        }

        .code-info {
            margin-top: 20px;
            padding: 15px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            font-size: 12px;
            color: #aaa;
        }

        /* Main Dashboard */
        .dashboard {
            display: none;
            min-height: 100vh;
            background: linear-gradient(135deg, #1a1a1a, #2d2d2d);
        }

        .header {
            background: rgba(0, 0, 0, 0.5);
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .menu-icon {
            font-size: 24px;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .menu-icon:hover {
            transform: rotate(90deg);
        }

        .profile-section {
            display: none;
            position: absolute;
            top: 70px;
            right: 20px;
            background: rgba(0, 0, 0, 0.9);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.5);
            z-index: 1000;
        }

        .profile-pic {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: #444;
            margin: 0 auto 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 30px;
            cursor: pointer;
            overflow: hidden;
        }

        .profile-pic img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .stats {
            display: flex;
            justify-content: space-around;
            padding: 20px;
            background: rgba(255, 255, 255, 0.05);
            margin: 20px;
            border-radius: 15px;
            flex-wrap: wrap;
        }

        .stat-item {
            text-align: center;
            padding: 10px;
        }

        .stat-item h3 {
            color: #ff6b6b;
            margin-bottom: 5px;
        }

        .menu-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            padding: 20px;
        }

        .menu-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 25px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s;
        }

        .menu-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }

        .menu-card h3 {
            color: #ff6b6b;
            margin-bottom: 15px;
            font-size: 20px;
        }

        .menu-card input, .menu-card select {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.1);
            color: #fff;
        }

        .menu-card button {
            width: 100%;
            padding: 10px;
            border: none;
            border-radius: 8px;
            background: linear-gradient(135deg, #ff6b6b, #ee5a24);
            color: #fff;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
        }

        .menu-card button:hover {
            transform: scale(1.05);
        }

        .result {
            margin-top: 15px;
            padding: 10px;
            border-radius: 8px;
            text-align: center;
            font-weight: bold;
        }

        .success {
            background: rgba(46, 213, 115, 0.2);
            color: #2ed573;
            border: 1px solid #2ed573;
        }

        .error {
            background: rgba(255, 71, 87, 0.2);
            color: #ff4757;
            border: 1px solid #ff4757;
        }

        .developer {
            text-align: center;
            padding: 20px;
            color: #666;
            font-size: 14px;
        }

        @media (max-width: 768px) {
            .menu-container {
                grid-template-columns: 1fr;
            }
            
            .stats {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Login Page -->
    <div class="login-container" id="loginPage">
        <div class="login-box">
            <div class="skull">💀</div>
            <h1>Selamat Datang Di Unbenned Akun WhatsApp V1</h1>
            <form id="loginForm">
                <div class="input-group">
                    <label>Username</label>
                    <input type="text" id="username" placeholder="Masukkan Username" required>
                </div>
                <div class="input-group">
                    <label>Password</label>
                    <input type="password" id="password" placeholder="Masukkan Password" required>
                </div>
                <div class="input-group">
                    <label>Nama</label>
                    <input type="text" id="nama" placeholder="Masukkan Nama Anda" required>
                </div>
                <div class="input-group">
                    <label>Kode (Optional)</label>
                    <input type="text" id="kode" placeholder="Masukkan Kode">
                </div>
                <div class="input-group">
                    <label>ID (Jika sudah punya akun)</label>
                    <input type="text" id="userId" placeholder="Masukkan ID">
                </div>
                <button type="submit" class="login-btn">MASUK</button>
            </form>
            <div class="code-info">
                <strong>Kode Tersedia:</strong><br>
                Nean831 = Admin 30 hari<br>
                Nean773 = Admin 2 hari<br>
                Nean80 = Admin 1 bulan<br>
                Nean99 = Admin Permanen<br>
                Nean01 = Member 2 bulan<br>
                Nean22 = Member permanen
            </div>
        </div>
    </div>

    <!-- Dashboard -->
    <div class="dashboard" id="dashboard">
        <div class="header">
            <h2>📱 Unbenned WhatsApp V1</h2>
            <div class="menu-icon" onclick="toggleProfile()">⋮⋮⋮</div>
        </div>

        <div class="profile-section" id="profileSection">
            <div class="profile-pic" onclick="changeProfilePic()">👤</div>
            <p><strong>Nama:</strong> <span id="profileName"></span></p>
            <p><strong>Anggota:</strong> <span id="profileRole"></span></p>
            <p><strong>ID:</strong> <span id="profileId"></span></p>
            <p><strong>Server:</strong> <span id="profileServer"></span></p>
        </div>

        <div class="stats">
            <div class="stat-item">
                <h3 id="totalUsers">0</h3>
                <p>Total User</p>
            </div>
            <div class="stat-item">
                <h3 id="onlineUsers">0</h3>
                <p>Online</p>
            </div>
            <div class="stat-item">
                <h3 id="battery">100%</h3>
                <p>Baterai</p>
            </div>
            <div class="stat-item">
                <h3 id="device">Android</h3>
                <p>Device</p>
            </div>
        </div>

        <div class="menu-container">
            <div class="menu-card">
                <h3>🔓 Menu Unbenned</h3>
                <input type="text" id="unbennedNumber" placeholder="628xxx">
                <select id="unbennedType">
                    <option value="">Pilih Type Benned</option>
                    <option value="spam">Benned Spam</option>
                    <option value="permanen">Benned Permanen</option>
                    <option value="batu">Benned Batu</option>
                </select>
                <button onclick="unbennedAccount()">PROSES UNBENNED</button>
                <div id="unbennedResult"></div>
            </div>

            <div class="menu-card" id="bennedMenu" style="display:none;">
                <h3>🔒 Menu Benned (Admin Only)</h3>
                <input type="text" id="bennedNumber" placeholder="628xxx">
                <select id="bennedBug">
                    <option value="">Pilih Bug</option>
                    <option value="delay">Bug Delay Android</option>
                    <option value="forcehard">Force Hard</option>
                    <option value="close">Force Close</option>
                </select>
                <select id="deviceType">
                    <option value="android">Android</option>
                    <option value="iphone">iPhone</option>
                </select>
                <button onclick="bennedAccount()">BUG NOMER</button>
                <div id="bennedResult"></div>
            </div>

            <div class="menu-card" id="spamMenu" style="display:none;">
                <h3>💬 Menu Spam NgL (Admin Only)</h3>
                <input type="text" id="spamUsername" placeholder="Masukkan Nama Username">
                <input type="text" id="spamMessage" placeholder="Masukkan pesan">
                <input type="number" id="spamCount" placeholder="Jumlah (9999999999)" max="9999999999">
                <button onclick="spamNGL()">SPAM NGL</button>
                <div id="spamResult"></div>
            </div>

            <div class="menu-card">
                <h3>🔍 Cek Benned WhatsApp</h3>
                <input type="text" id="cekNumber" placeholder="628xxx">
                <button onclick="cekBenned()">CEK NOMER</button>
                <div id="cekResult"></div>
            </div>
        </div>

        <div class="developer">
            <p>Developer: Hasnan-Nean</p>
        </div>
    </div>

    <script>
        // Kode-kode yang tersedia (simulasi)
        const availableCodes = [
            'Nean831', 'Nean773', 'Nean80', 'Nean99', 'Nean01', 'Nean22',
            'Nean202', 'Nean303', 'Nean404', 'Nean505', 'Nean606', 'Nean707'
        ];

        // User data simulation
        let currentUser = null;
        let userRole = 'member';
        let userExpiry = null;

        // Login function
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const nama = document.getElementById('nama').value;
            const kode = document.getElementById('kode').value;
            const userId = document.getElementById('userId').value;

            // Validasi default
            if (username === 'Nean' && password === 'Nean123') {
                currentUser = {
                    username: username,
                    nama: nama || 'User',
                    role: 'member',
                    id: userId || generateId()
                };

                // Cek kode
                if (kode && availableCodes.includes(kode)) {
                    if (kode === 'Nean99' || kode === 'Nean22') {
                        currentUser.role = 'admin';
                        userRole = 'admin';
                    } else if (kode === 'Nean831' || kode === 'Nean773' || kode === 'Nean80' || kode === 'Nean01') {
                        currentUser.role = 'admin';
                        userRole = 'admin';
                        // Set expiry date
                        const days = kode === 'Nean831' ? 30 : kode === 'Nean773' ? 2 : kode === 'Nean80' ? 30 : 60;
                        userExpiry = new Date();
                        userExpiry.setDate(userExpiry.getDate() + days);
                    }
                }

                // Tampilkan dashboard
                document.getElementById('loginPage').style.display = 'none';
                document.getElementById('dashboard').style.display = 'block';
                
                // Update profile
                document.getElementById('profileName').textContent = currentUser.nama;
                document.getElementById('profileRole').textContent = userRole === 'admin' ? 'Admin' : 'Member';
                document.getElementById('profileId').textContent = currentUser.id;
                document.getElementById('profileServer').textContent = userRole === 'admin' && !userExpiry ? 'Permanen' : 
                    userExpiry ? `${Math.ceil((userExpiry - new Date()) / (1000 * 60 * 60 * 24))} hari lagi` : 'Free';

                // Tampilkan menu admin jika admin
                if (userRole === 'admin') {
                    document.getElementById('bennedMenu').style.display = 'block';
                    document.getElementById('spamMenu').style.display = 'block';
                }

                // Update stats
                updateStats();
            } else {
                alert('Username atau Password salah!');
            }
        });

        function generateId() {
            return 'ID' + Math.random().toString(36).substr(2, 9).toUpperCase();
        }

        function toggleProfile() {
            const profile = document.getElementById('profileSection');
            profile.style.display = profile.style.display === 'none' ? 'block' : 'none';
        }

        function changeProfilePic() {
            const input = document.createElement('input');
            input.type = 'file';
            input.accept = 'image/*';
            input.onchange = function(e) {
                const file = e.target.files[0];
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.querySelector('.profile-pic').innerHTML = `<img src="${e.target.result}" alt="Profile">`;
                };
                reader.readAsDataURL(file);
            };
            input.click();
        }

        function updateStats() {
            // Simulasi update stats
            document.getElementById('totalUsers').textContent = Math.floor(Math.random() * 1000) + 500;
            document.getElementById('onlineUsers').textContent = Math.floor(Math.random() * 100) + 20;
            document.getElementById('battery').textContent = Math.floor(Math.random() * 50) + 50 + '%';
        }

        function unbennedAccount() {
            const number = document.getElementById('unbennedNumber').value;
            const type = document.getElementById('unbennedType').value;
            const result = document.getElementById('unbennedResult');
            
            if (!number || !type) {
                result.className = 'result error';
                result.textContent = 'Harap isi semua field!';
                return;
            }

            // Simulasi proses
            setTimeout(() => {
                const success = Math.random() > 0.3;
                if (success) {
                    result.className = 'result success';
                    result.textContent = `Akun Anda Berhasil Di Pulihkan! Tunggu selama ${Math.floor(Math.random() * 24) + 1} jam`;
                } else {
                    result.className = 'result error';
                    result.textContent = 'Akun Anda Gagal di pulihkan harap coba lagi';
                }
            }, 2000);
        }

        function bennedAccount() {
            if (userRole !== 'admin') {
                alert('Menu ini hanya untuk admin!');
                return;
            }

            const number = document.getElementById('bennedNumber').value;
            const bug = document.getElementById('bennedBug').value;
            const result = document.getElementById('bennedResult');
            
            if (!number || !bug) {
                result.className = 'result error';
                result.textContent = 'Harap isi semua field!';
                return;
            }

            setTimeout(() => {
                const success = Math.random() > 0.2;
                if (success) {
                    result.className = 'result success';
                    result.textContent = 'Nomer berhasil di bug!';
                } else {
                    result.className = 'result error';
                    result.textContent = 'Nomer gagal di bug harap coba lagi';
                }
            }, 1500);
        }

        function spamNGL() {
            if (userRole !== 'admin') {
                alert('Menu ini hanya untuk admin!');
                return;
            }

            const username = document.getElementById('spamUsername').value;
            const message = document.getElementById('spamMessage').value;
            const count = document.getElementById('spamCount').value;
            const result = document.getElementById('spamResult');
            
            if (!username || !message || !count) {
                result.className = 'result error';
                result.textContent = 'Harap isi semua field!';
                return;
            }

            setTimeout(() => {
                result.className = 'result success';
                result.textContent = 'Berhasil Semua, Sistem tidak bisa deteksi tapi 100% berhasil';
            }, 1000);
        }

        function cekBenned() {
            const number = document.getElementById('cekNumber').value;
            const result = document.getElementById('cekResult');
            
            if (!number) {
                result.className = 'result error';
                result.textContent = 'Harap masukkan nomer!';
                return;
            }

            setTimeout(() => {
                const isActive = Math.random() > 0.4;
                if (isActive) {
                    result.className = 'result success';
                    result.textContent = 'Nomer Ini Masih Aktif ☺️';
                } else {
                    result.className = 'result error';
                    result.textContent = 'Nomer Ini Tidak Aktif 🔥💥☠️😈';
                }
            }, 1000);
        }

        // Update stats setiap 5 detik
        setInterval(updateStats, 5000);
    </script>
</body>
</html>
