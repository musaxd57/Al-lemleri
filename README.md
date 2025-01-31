<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Satın Alma Sayfası</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .form-group {
            margin-bottom: 15px;
        }
        label {
            display: block;
            margin-bottom: 5px;
        }
        input, select {
            width: 100%;
            padding: 8px;
            box-sizing: border-box;
        }
        button {
            padding: 10px 15px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

    <h2>Satın Alma Sayfası</h2>
    <form id="purchase-form">
        <div class="form-group">
            <label for="card-number">Kredi Kartı Numarası:</label>
            <input type="text" id="card-number" placeholder="Kart Numarası" required>
        </div>
        <div class="form-group">
            <label for="expiry-date">Son Kullanma Tarihi:</label>
            <select id="expiry-month" required>
                <option value="" disabled selected>Ay</option>
                <option value="01">01</option>
                <option value="02">02</option>
                <!-- Diğer ayları buraya ekleyebilirsiniz -->
            </select>
            <select id="expiry-year" required>
                <option value="" disabled selected>Yıl</option>
                <option value="2025">2025</option>
                <option value="2026">2026</option>
                <!-- Diğer yılları buraya ekleyebilirsiniz -->
            </select>
        </div>
        <div class="form-group">
            <label for="cvv">CVV:</label>
            <input type="text" id="cvv" placeholder="CVV" required>
        </div>
        <button type="submit">Ödeme Yap</button>
    </form>

    <script>
        document.getElementById("purchase-form").addEventListener("submit", function(event) {
            event.preventDefault();
            alert("Ödeme Başarıyla Yapıldı!");
        });
    </script>

</body>
</html>
