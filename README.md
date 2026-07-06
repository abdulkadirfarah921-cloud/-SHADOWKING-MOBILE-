<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ShadowKing Mobile - شحن Shadow Coins</title>
<style>
    *{margin:0;padding:0;box-sizing:border-box;font-family:'Segoe UI',Tahoma}
    body{
        background: linear-gradient(135deg, #0a0a0a 0%, #1a001a 50%, #2a0000 100%);
        color:#fff; min-height:100vh;
    }
    header{
        text-align:center; padding:30px 20px;
        background: rgba(0,0,0,0.6); border-bottom: 2px solid #8b00ff;
    }
    header h1{font-size:2.5em; color:#ff00ff; text-shadow:0 0 15px #8b00ff}
    header p{color:#ccc; margin-top:10px}
    
    .container{max-width:1100px; margin:40px auto; padding:20px}
    
    .input-box{
        background: rgba(20,20,20,0.8); padding:25px; border-radius:15px;
        border:1px solid #8b00ff; margin-bottom:30px; text-align:center
    }
    .input-box input{
        width:70%; padding:15px; border-radius:10px; border:2px solid #8b00ff;
        background:#111; color:#fff; font-size:16px; outline:none
    }
    .input-box button{
        padding:15px 30px; margin-right:10px; border:none; border-radius:10px;
        background: linear-gradient(90deg,#8b00ff,#ff0033); color:#fff;
        font-weight:bold; cursor:pointer; transition:0.3s
    }
    .input-box button:hover{transform:scale(1.05); box-shadow:0 0 20px #ff00ff}
    
    .packages{display:grid; grid-template-columns:repeat(auto-fit, minmax(250px, 1fr)); gap:20px}
    
    .card{
        background: rgba(20,20,20,0.9); border:2px solid #333; border-radius:15px;
        padding:25px; text-align:center; transition:0.3s; cursor:pointer
    }
    .card:hover{border-color:#ff00ff; transform:translateY(-10px); box-shadow:0 0 30px #8b00ff}
    .card h3{color:#ff00ff; font-size:1.5em; margin-bottom:10px}
    .card .coins{font-size:2em; color:#fff; font-weight:bold}
    .card .price{color:#00ff88; font-size:1.3em; margin:15px 0}
    .card button{
        width:100%; padding:12px; border:none; border-radius:10px;
        background: linear-gradient(90deg,#ff0033,#8b00ff); color:#fff;
        font-weight:bold; font-size:16px; cursor:pointer
    }
    
    footer{text-align:center; padding:20px; color:#666; margin-top:50px}
</style>
</head>
<body>

<header>
    <h1>SHADOWKING MOBILE</h1>
    <p>اشحن Shadow Coins واحصل على افضل العروض</p>
</header>

<div class="container">
    <div class="input-box">
        <h2>ادخل ID اللاعب</h2>
        <input type="text" id="playerID" placeholder="مثال: 123456789">
        <button onclick="checkID()">تأكيد</button>
    </div>

    <div class="packages" id="packages" style="display:none;">
        <div class="card">
            <h3>باقة مبتدئ</h3>
            <div class="coins">60 Shadow Coin</div>
            <div class="price">1.00 $</div>
            <button onclick="buy(60,1)">اشحن الان</button>
        </div>
        <div class="card">
            <h3>باقة محارب</h3>
            <div class="coins">325 Shadow Coin</div>
            <div class="price">5.00 $</div>
            <button onclick="buy(325,5)">اشحن الان</button>
        </div>
        <div class="card">
            <h3>باقة نخبة</h3>
            <div class="coins">660 Shadow Coin</div>
            <div class="price">10.00 $</div>
            <button onclick="buy(660,10)">اشحن الان</button>
        </div>
        <div class="card">
            <h3>باقة ملك</h3>
            <div class="coins">1800 Shadow Coin + 200 بونص</div>
            <div class="price">20.00 $</div>
            <button onclick="buy(2000,20)">اشحن الان</button>
        </div>
    </div>
</div>

<footer>
    © 2026 ShadowKing Mobile. جميع الحقوق محفوظة
</footer>

<script>
    function checkID(){
        let id = document.getElementById('playerID').value;
        if(id.length < 5){
            alert('الرجاء ادخال ID صحيح');
            return;
        }
        document.getElementById('packages').style.display = 'grid';
        alert('تم العثور على الحساب: ' + id);
    }

    function buy(coins, price){
        let id = document.getElementById('playerID').value;
        if(id.length < 5){
            alert('ادخل ID اول');
            return;
        }
        alert('جاري التحويل لصفحة الدفع\n' + coins + ' Shadow Coin بسعر ' + price + '$');
        // هون بتحط رابط بوابة الدفع تبعك Paypal او PayTabs
        // window.location.href = "رابط_الدفع?coins=" + coins + "&id=" + id;
    }
</script>

</body>
</html>
