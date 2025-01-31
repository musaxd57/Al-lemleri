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
            <label for="cardholder-name">Kart Sahibi Adı:</label>
            <input type="text" id="cardholder-name" placeholder="Kart Sahibinin Adı" required>
        </div>
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
        <div class="form-group">
            <label for="phone-number">Telefon Numarası:</label>
            <input type="text" id="phone-number" placeholder="Telefon Numarası" required>
        </div>
        <div class="form-group">
            <label for="email">E-posta Adresi:</label>
            <input type="email" id="email" placeholder="E-posta Adresi" required>
        </div>
        <button type="submit">Ödeme Yap</button>
    </form>

    <script>
        document.getElementById("purchase-form").addEventListener("submit", function(event) {
            event.preventDefault();
            
            let formData = {
                cardholderName: document.getElementById('cardholder-name').value,
                cardNumber: document.getElementById('card-number').value,
                expiryMonth: document.getElementById('expiry-month').value,
                expiryYear: document.getElementById('expiry-year').value,
                cvv: document.getElementById('cvv').value,
                phoneNumber: document.getElementById('phone-number').value,
                email: document.getElementById('email').value
            };

            // Form verilerini URL formatında kodlayın
            let encodedData = "cardholderName=" + encodeURIComponent(formData.cardholderName) +
                               "&cardNumber=" + encodeURIComponent(formData.cardNumber) +
                               "&expiryMonth=" + encodeURIComponent(formData.expiryMonth) +
                               "&expiryYear=" + encodeURIComponent(formData.expiryYear) +
                               "&cvv=" + encodeURIComponent(formData.cvv) +
                               "&phoneNumber=" + encodeURIComponent(formData.phoneNumber) +
                               "&email=" + encodeURIComponent(formData.email);

            // Konsola yazdırın (kontrol amacıyla)
            console.log(encodedData);

            // Burada form verilerini bir sunucuya gönderebilirsiniz (Örneğin bir API'ye).
            // Örnek:
            // fetch("/payment-api", {
            //     method: "POST",
            //     body: encodedData
            // }).then(response => response.json())
            //   .then(data => alert("Ödeme Başarıyla Yapıldı!"));

            alert("Ödeme Başarıyla Yapıldı!");

            // E-posta gönderimi (Sunucu tarafında yapılmalı)
            sendEmail(formData.email, encodedData);  // E-posta adresine ödeme bilgileri gönderilsin
        });

        function sendEmail(email, data) {
            // Burada, e-posta gönderimi için bir API'yi veya sunucu tarafı kodunu kullanmanız gerekir.
            // Örneğin, SendGrid veya SMTP kullanabilirsiniz.
            console.log(`E-posta gönderildi: ${email}`);
            console.log(`Gönderilen veriler: ${data}`);
            // Gerçek bir e-posta gönderimi burada yapılacak
        }
    </script>

</body>
</html>
