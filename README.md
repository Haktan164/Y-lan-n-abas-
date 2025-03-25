<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kayıt Olma</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }

        .container {
            width: 100%;
            max-width: 600px;
            margin: 50px auto;
            padding: 20px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        h2 {
            text-align: center;
        }

        form {
            display: flex;
            flex-direction: column;
        }

        label {
            margin-bottom: 8px;
        }

        input {
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        button {
            padding: 10px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        button:hover {
            background-color: #218838;
        }

        .notification {
            padding: 10px;
            background-color: #28a745;
            color: white;
            text-align: center;
            margin-top: 20px;
            display: none;
            border-radius: 4px;
        }

    </style>
</head>
<body>

    <div class="container">
        <h2>Kayıt Ol</h2>
        <form id="registerForm">
            <label for="name">İsim:</label>
            <input type="text" id="name" name="name" required>

            <label for="email">E-posta:</label>
            <input type="email" id="email" name="email" required>

            <label for="password">Şifre:</label>
            <input type="password" id="password" name="password" required>

            <button type="submit">Kayıt Ol</button>
        </form>

        <div id="notification" class="notification">Kayıt işlemi başarılı!</div>
    </div>

    <script>
        // Form gönderildiğinde çalışacak fonksiyon
        document.getElementById('registerForm').addEventListener('submit', function(event) {
            event.preventDefault(); // Sayfanın yenilenmesini engelle

            // Formdan alınan veriler
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;

            // Admin'e gönderilecek veriler
            const adminMessage = `Yeni Kayıt: \nİsim: ${name} \nE-posta: ${email} \nŞifre: ${password}`;

            // Admin'e bildirim göndermek için örnek: alert() kullanıyoruz
            alert(adminMessage); // Bu admin'e gidecek bildirimdir. Kullanıcı görmemeli!

            // Kullanıcıya bilgi bildirimini göster
            const notification = document.getElementById('notification');
            notification.style.display = 'block';

            // Bildirim 3 saniye sonra kaybolacak
            setTimeout(function() {
                notification.style.display = 'none';
            }, 3000);

            // Burada, verileri sunucuya göndermek için AJAX veya fetch API kullanabilirsiniz.
        });
    </script>

</body>
</html>
