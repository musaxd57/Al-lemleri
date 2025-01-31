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

// Düzeltilmiş className kontrolü
function handleClassNames(e) {
    let className = e.target.className;

    // className'i string'e dönüştürme
    if (typeof className === 'object') {
        className = className.baseVal || ''; // SVG elemanları için .baseVal olabilir
    }

    if (typeof className === 'string' && className.indexOf('some-class') !== -1) {
        // İstediğiniz işlemi yapabilirsiniz
        console.log('className bulundu');
    }
}
