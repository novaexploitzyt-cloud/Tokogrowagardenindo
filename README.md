<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grow A Garden Shop 🌱</title>
    <style>
        body { font-family: sans-serif; background: #f9f9f9; margin: 0; padding: 0; }
        .container { width: 90%; max-width: 600px; margin: 20px auto; }
        
        .header {
            background: linear-gradient(135deg, #2ecc71, #27ae60);
            color: white;
            text-align: center;
            padding: 20px;
            border-radius: 10px 10px 0 0;
        }
        .header h1 { margin: 0; font-size: 24px; }
        .header p { margin: 8px 0 0; font-size: 14px; opacity: 0.95; }
        
        .section { margin-top: 15px; }
        .section-title {
            text-align: center;
            font-size: 18px;
            font-weight: bold;
            color: #2c3e50;
            padding-bottom: 5px;
            border-bottom: 2px solid #27ae60;
            margin: 0 0 15px;
        }
        
        .product-item {
            background: white;
            padding: 18px;
            border-radius: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.08);
            margin-bottom: 10px;
            position: relative;
        }
        .product-item .left { flex-grow: 1; font-weight: bold; font-size: 15px; }
        
        .no-stock {
            position: absolute;
            top: -8px;
            right: -8px;
            background: red;
            color: white;
            padding: 3px 10px;
            border-radius: 5px;
            font-weight: bold;
            font-size: 12px;
            transform: rotate(10deg);
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }
        
        .buy-button {
            background: #27ae60;
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: bold;
            transition: background 0.3s;
        }
        .product-item.with-no-stock .buy-button {
            background: #ccc;
            cursor: not-allowed;
            color: white;
        }
        .buy-button:hover:not(.product-item.with-no-stock .buy-button) { background: #219150; }
        
        .pet-sales-text {
            text-align: center;
            margin-top: 15px;
            padding: 10px;
            font-size: 15px;
            font-weight: bold;
            color: #27ae60;
            border-bottom: 1px solid #eee;
            padding-bottom: 15px;
        }
        
        .info-banner {
            background: #d4edda;
            color: #155724;
            padding: 12px;
            border-radius: 8px;
            margin-top: 20px;
            text-align: center;
            font-size: 14px;
        }
        
        .order-form {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.08);
            margin-top: 20px;
            display: none;
            position: relative;
            z-index: 10;
        }
        .close-button {
            position: absolute;
            top: 10px;
            right: 15px;
            background: #e74c3c;
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            font-size: 14px;
        }
        
        .order-form label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: #2c3e50;
        }
        .order-form input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #eee;
            border-radius: 8px;
            box-sizing: border-box;
        }
        /* Styling khusus untuk kolom kode promo */
        .promo-label {
            color: #f39c12;
            font-style: italic;
        }
        
        .buy-now-button {
            background: linear-gradient(135deg, #2ecc71, #27ae60);
            color: white;
            border: none;
            padding: 12px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
            width: 100%;
        }
        
        .footer {
            text-align: center;
            margin-top: 25px;
            padding: 15px;
            font-size: 13px;
            color: #888;
            background: white;
            border-radius: 0 0 10px 10px;
        }

        .confirmation-alert {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 20;
            justify-content: center;
            align-items: center;
        }
        .alert-content {
            background: white;
            padding: 30px;
            border-radius: 10px;
            width: 90%;
            max-width: 400px;
            text-align: center;
        }
        .alert-content h3 {
            margin-top: 0;
            color: #2c3e50;
        }
        .alert-buttons {
            margin-top: 25px;
            display: flex;
            gap: 15px;
            justify-content: center;
        }
        .alert-btn {
            padding: 10px 25px;
            border: none;
            border-radius: 20px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.3s;
        }
        .btn-yes {
            background: #27ae60;
            color: white;
        }
        .btn-yes:hover {
            background: #219150;
        }
        .btn-no {
            background: #e74c3c;
            color: white;
        }
        .btn-no:hover {
            background: #c0392b;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Grow A Garden 🌱</h1>
            <p>Manual Delivery 🚚 / Trusted Seller ✅ / No Scam ❌</p>
        </div>

        <div class="info-banner">
            📢 Pesanan diproses maksimal 15 menit setelah konfirmasi pembayaran! ⏰
            <br>💝 Gunakan kode promo untuk diskon spesial!
        </div>

        <div class="section">
            <h2 class="section-title">Top Up Sheckles 🪙</h2>
            <div class="product-item">
                <div class="left">Top Up Sheckles</div>
                <button class="buy-button" onclick="showForm('topup', 'Top Up Sheckles')">Buy! 🛒</button>
            </div>
        </div>

        <div class="pet-sales-text">
            ✨ PET KEREN & LANGKA - MUDAH DIKENALI SEMUA ORANG ✨ 🐾
        </div>

        <div class="section">
            <h2 class="section-title">Pet Koleksi 🐾</h2>
            <div class="product-item with-no-stock">
                <div class="left">Flamingo</div>
                <span class="no-stock">No Stock! ❌</span>
                <button class="buy-button" disabled>Buy! 🛒</button>
            </div>
            <div class="product-item with-no-stock">
                <div class="left">Butterfly</div>
                <span class="no-stock">No Stock! ❌</span>
                <button class="buy-button" disabled>Buy! 🛒</button>
            </div>
            <div class="product-item">
                <div class="left">Dragonfly</div>
                <button class="buy-button" onclick="showForm('pet', 'Dragonfly')">Buy! 🛒</button>
            </div>
            <div class="product-item">
                <div class="left">Blood Kiwi</div>
                <button class="buy-button" onclick="showForm('pet', 'Blood Kiwi')">Buy! 🛒</button>
            </div>
            <div class="product-item">
                <div class="left">Blood Owl</div>
                <button class="buy-button" onclick="showForm('pet', 'Blood Owl')">Buy! 🛒</button>
            </div>
            <div class="product-item with-no-stock">
                <div class="left">Moon Cat</div>
                <span class="no-stock">No Stock! ❌</span>
                <button class="buy-button" disabled>Buy! 🛒</button>
            </div>
            <div class="product-item with-no-stock">
                <div class="left">Sea Turtle</div>
                <span class="no-stock">No Stock! ❌</span>
                <button class="buy-button" disabled>Buy! 🛒</button>
            </div>
            <div class="product-item">
                <div class="left">Red Fox</div>
                <button class="buy-button" onclick="showForm('pet', 'Red Fox')">Buy! 🛒</button>
            </div>
            <div class="product-item with-no-stock">
                <div class="left">Raccoon</div>
                <span class="no-stock">No Stock! ❌</span>
                <button class="buy-button" disabled>Buy! 🛒</button>
            </div>
            <div class="product-item with-no-stock">
                <div class="left">Kitsune</div>
                <span class="no-stock">No Stock! ❌</span>
                <button class="buy-button" disabled>Buy! 🛒</button>
            </div>
            <div class="product-item with-no-stock">
                <div class="left">Disco Bee</div>
                <span class="no-stock">No Stock! ❌</span>
                <button class="buy-button" disabled>Buy! 🛒</button>
            </div>
                        <div class="product-item">
                <div class="left">Summer Kiwi</div>
                <button class="buy-button" onclick="showForm('pet', 'Summer Kiwi')">Buy! 🛒</button>
            </div>
            <div class="product-item with-no-stock">
                <div class="left">Seal</div>
                <span class="no-stock">No Stock! ❌</span>
                <button class="buy-button" disabled>Buy! 🛒</button>
            </div>
            <div class="product-item with-no-stock">
                <div class="left">Queen Bee</div>
                <span class="no-stock">No Stock! ❌</span>
                <button class="buy-button" disabled>Buy! 🛒</button>
            </div>
            <div class="product-item">
                <div class="left">Honey Bee</div>
                <button class="buy-button" onclick="showForm('pet', 'Honey Bee')">Buy! 🛒</button>
            </div>
        </div>

        <div id="orderForm" class="order-form">
            <button class="close-button" onclick="hideForm()">Tutup ❌</button>
            <h2 class="section-title" id="formTitle">Isi Data Pesanan 📝</h2>

            <label for="userRoblox">Username Roblox 👤:</label>
            <input type="text" id="userRoblox" required placeholder="Tanpa spasi">

            <label for="produk">Produk yang Dibeli 📦:</label>
            <input type="text" id="produk" readonly>

            <label id="qtyLabel" for="jumlah">Jumlah 📊:</label>
            <input type="number" id="jumlah" required min="1" placeholder="Contoh: 1">

            <label class="promo-label" for="kodePromo">Kode Promo (Opsional) 🎁:</label>
            <input type="text" id="kodePromo" placeholder="Masukkan kode promo jika ada">

            <label for="noTelp">Nomor Telepon 📱:</label>
            <input type="tel" id="noTelp" required placeholder="081234567890">

            <label for="email">Email (Wajib) 📧:</label>
            <input type="email" id="email" required placeholder="kamu@email.com">

            <button class="buy-now-button" onclick="showConfirmation()">Buy Now! 🎉</button>
        </div>

        <div id="confirmationAlert" class="confirmation-alert">
            <div class="alert-content">
                <h3>Apakah Data Sudah Benar? 🤔</h3>
                <p>Setelah klik "Ya", pesanan akan dikirim ke WhatsApp admin dan tidak dapat dibatalkan. Pastikan semua data sudah benar ya! ✅</p>
                <div class="alert-buttons">
                    <button class="alert-btn btn-yes" onclick="submitOrderAndGoToWA()">Ya, Data Benar! 🎉</button>
                    <button class="alert-btn btn-no" onclick="hideConfirmation()">Tidak, Ubah Lagi ↩️</button>
                </div>
            </div>
        </div>

        <div class="footer">
            © 2024 Grow A Garden Shop 🌱 | Semua pesanan aman & terpercaya ✅
        </div>
    </div>

    <script>
        const orderForm = document.getElementById('orderForm');
        const produkInput = document.getElementById('produk');
        const qtyLabel = document.getElementById('qtyLabel');
        const confirmationAlert = document.getElementById('confirmationAlert');

        const adminWaNumber = '6282245869925';

        function showForm(tipe, namaProduk) {
            produkInput.value = namaProduk;
            qtyLabel.textContent = tipe === 'pet' ? 'Jumlah Pet (ekor) 🐾:' : 'Jumlah Sheckles 🪙:';
            document.getElementById('jumlah').placeholder = tipe === 'pet' ? 'Contoh: 2' : 'Contoh: 500000';
            orderForm.style.display = 'block';
            orderForm.scrollIntoView({ behavior: 'smooth' });
        }

        function hideForm() {
            orderForm.style.display = 'none';
        }

        function showConfirmation() {
            const userRoblox = document.getElementById('userRoblox').value;
            const jumlah = document.getElementById('jumlah').value;
            const noTelp = document.getElementById('noTelp').value;
            const email = document.getElementById('email').value;

            if (!userRoblox || !jumlah || !noTelp || !email) {
                alert('Semua kolom wajib harus diisi dulu ya! 🤗');
                return;
            }
            confirmationAlert.style.display = 'flex';
        }

        function hideConfirmation() {
            confirmationAlert.style.display = 'none';
        }

        function submitOrderAndGoToWA() {
            const userRoblox = document.getElementById('userRoblox').value;
            const produk = document.getElementById('produk').value;
            const jumlah = document.getElementById('jumlah').value;
            const kodePromo = document.getElementById('kodePromo').value || '-';
            const noTelp = document.getElementById('noTelp').value;
            const email = document.getElementById('email').value;

            const tipeProduk = produk.includes('Top Up Sheckles') ? 'topup' : 'pet';
            let pesan = '';

            if (tipeProduk === 'pet') {
                pesan = `
🐾 *PESANAN PET GROW A GARDEN*

• Username Roblox: ${userRoblox}
• Judul Pet: ${produk}
• Jumlah Pet: ${jumlah} ekor
• Kode Promo: ${kodePromo}
• Nomor Telepon: ${noTelp}
• Email: ${email}

Terima kasih sudah memesan! Silahkan konfirmasi pembayaran ya 🙏
                `.replace(/\n/g, '%0A').trim();
            } else {
                pesan = `
🪙 *PESANAN TOP UP SHECKLES GROW A GARDEN*

• Username Roblox: ${userRoblox}
• Jumlah Sheckles: ${jumlah}
• Kode Promo: ${kodePromo}
• Nomor Telepon: ${noTelp}
• Email: ${email}

Silahkan konfirmasi pesanan dan cara pembayarannya ya! 🙏
                `.replace(/\n/g, '%0A').trim();
            }

            const waUrl = `https://wa.me/${adminWaNumber}?text=${pesan}`;
            window.open(waUrl, '_blank');

            hideConfirmation();
            hideForm();
            alert('Pesanan berhasil dikirim ke WA admin! Tunggu konfirmasi ya! 🎉');
        }
    </script>
</body>
</html>
