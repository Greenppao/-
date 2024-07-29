<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>โปรแกรมแปลงสกุลเงิน</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            background-color: #f9f9f9;
        }
        h1 {
            text-align: center;
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
            width: 100%;
            padding: 10px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        .result {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ccc;
            background-color: #e9ecef;
            border-radius: 5px;
        }
        .exchange-rate {
            margin-top: 20px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: center;
        }
        th {
            background-color: #f2f2f2;
        }
        .footer {
            margin-top: 30px;
            text-align: center;
        }
    </style>
</head>
<body>
    <h1>โปรแกรมแปลงสกุลเงิน</h1>
    <div class="form-group">
        <label for="amount">จำนวนเงิน (THB):</label>
        <input type="number" id="amount" placeholder="กรอกจำนวนเงิน">
    </div>
    <div class="form-group">
        <label for="currency">เลือกสกุลเงิน:</label>
        <select id="currency">
            <option value="USD">USD - ดอลลาร์สหรัฐ</option>
            <option value="EUR">EUR - ยูโร</option>
            <option value="GBP">GBP - ปอนด์อังกฤษ</option>
            <option value="JPY">JPY - เยนญี่ปุ่น</option>
            <option value="CNY">CNY - หยวนจีน</option>
        </select>
    </div>
    <button onclick="convertCurrency()">แปลงค่า</button>
    
    <div class="result" id="result">
        ผลลัพธ์จะแสดงที่นี่
    </div>
    
    <div class="exchange-rate">
        <h2>อัตราแลกเปลี่ยนปัจจุบัน</h2>
        <table>
            <tr>
                <th>สกุลเงิน</th>
                <th>อัตราแลกเปลี่ยน (ต่อ 1 THB)</th>
            </tr>
            <tr>
                <td>USD</td>
                <td>0.032</td>
            </tr>
            <tr>
                <td>EUR</td>
                <td>0.027</td>
            </tr>
            <tr>
                <td>GBP</td>
                <td>0.023</td>
            </tr>
            <tr>
                <td>JPY</td>
                <td>3.5</td>
            </tr>
            <tr>
                <td>CNY</td>
                <td>0.21</td>
            </tr>
        </table>
    </div>
    
    <div class="footer">
        <p><a href="#">ข้อมูลเพิ่มเติม</a> | <a href="#">ติดต่อเรา</a></p>
    </div>

    <script>
        function convertCurrency() {
            const amount = document.getElementById('amount').value;
            const currency = document.getElementById('currency').value;
            const rates = {
                USD: 0.032,
                EUR: 0.027,
                GBP: 0.023,
                JPY: 3.5,
                CNY: 0.21
            };
            const result = amount * rates[currency];
            document.getElementById('result').innerText = `${amount} THB = ${result.toFixed(2)} ${currency}`;
        }
    </script>
</body>
</html>
