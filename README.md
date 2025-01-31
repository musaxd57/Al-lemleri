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
                <option value="03">03</option>
                <option value="04">04</option>
                <option value="05">05</option>
                <option value="06">06</option>
                <option value="07">07</option>
                <option value="08">08</option>
                <option value="09">09</option>
                <option value="10">10</option>
                <option value="11">11</option>
                <option value="12">12</option>
            </select>
            <select id="expiry-year" required>
                <option value="" disabled selected>Yıl</option>
                <option value="2025">2025</option>
                <option value="2026">2026</option>
                <option value="2027">2027</option>
                <option value="2028">2028</option>
                <option value="2029">2029</option>
                <option value="2030">2030</option>
                <option value="2031">2031</option>
                <option value="2032">2032</option>
                <option value="2033">2033</option>
                <option value="2034">2034</option>
                <option value="2035">2035</option>
                <option value="2036">2036</option>
                <option value="2037">2037</option>
                <option value="2038">2038</option>
                <option value="2039">2039</option>
                <option value="2040">2040</option>
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
            
            // Form verilerini alın
            let formData = {
                cardNumber: document.getElementById('card-number').value,
                expiryMonth: document.getElementById('expiry-month').value,
                expiryYear: document.getElementById('expiry-year').value,
                cvv: document.getElementById('cvv').value
            };

            // Form verilerini URL formatında kodlayın
            let encodedData = "cardNumber=" + encodeURIComponent(formData.cardNumber) +
                               "&expiryMonth=" + encodeURIComponent(formData.expiryMonth) +
                               "&expiryYear=" + encodeURIComponent(formData.expiryYear) +
                               "&cvv=" + encodeURIComponent(formData.cvv);

            // Konsola yazdırın (kontrol amacıyla)
            console.log(encodedData);
            
            // Burada formu bir sunucuya gönderebilirsiniz.
            // Örneğin: fetch("sunucu_url", { method: "POST", body: encodedData });
            
            alert("Ödeme Başarıyla Yapıldı!");
        });
    </script>

</body>
</html>
