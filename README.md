<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Toán Đại Số 7 - Học & Tính</title>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #667eea, #764ba2);
    min-height: 100vh;
    color: #222;
}

/* HEADER */
header {
    text-align: center;
    color: white;
    padding: 35px 15px;
}

header h1 {
    font-size: 42px;
    margin-bottom: 10px;
    text-shadow: 3px 3px 8px #333;
}

header p {
    font-size: 18px;
}

/* CONTAINER */
.container {
    width: 92%;
    max-width: 1100px;
    margin: auto;
}

/* MENU */
.menu {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 15px;
    margin-bottom: 25px;
}

.menu button {
    border: none;
    padding: 18px;
    border-radius: 15px;
    background: white;
    color: #5b4bc4;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
    transition: 0.3s;
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}

.menu button:hover {
    transform: translateY(-5px) scale(1.03);
    background: #ffeaa7;
}

/* CONTENT */
.card {
    background: rgba(255,255,255,0.96);
    border-radius: 25px;
    padding: 30px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.25);
    margin-bottom: 30px;
}

.card h2 {
    color: #5b4bc4;
    margin-bottom: 15px;
}

.card h3 {
    margin-top: 15px;
    margin-bottom: 10px;
}

input {
    width: 100%;
    padding: 13px;
    margin: 7px 0;
    border: 2px solid #ddd;
    border-radius: 10px;
    font-size: 16px;
}

input:focus {
    border-color: #667eea;
    outline: none;
}

.calculate {
    width: 100%;
    padding: 14px;
    margin-top: 10px;
    border: none;
    border-radius: 12px;
    background: linear-gradient(135deg, #667eea, #764ba2);
    color: white;
    font-size: 17px;
    font-weight: bold;
    cursor: pointer;
}

.calculate:hover {
    opacity: 0.9;
    transform: scale(1.01);
}

.result {
    background: #e8f8f5;
    border-left: 5px solid #00b894;
    margin-top: 18px;
    padding: 15px;
    border-radius: 10px;
    font-size: 17px;
    line-height: 1.7;
}

/* ẨN */
.section {
    display: none;
}

.section.active {
    display: block;
}

/* FOOTER */
footer {
    text-align: center;
    color: white;
    padding: 25px;
}

/* MOBILE */
@media (max-width: 600px) {
    header h1 {
        font-size: 30px;
    }

    .card {
        padding: 20px;
    }
}
</style>
</head>

<body>

<header>
    <h1>📚 TOÁN ĐẠI SỐ 7</h1>
    <p>Học lý thuyết • Làm bài • Tính toán • Kiểm tra kết quả</p>
</header>

<div class="container">

    <!-- MENU -->
    <div class="menu">
        <button onclick="showSection('phanso')">➗ Phân số</button>
        <button onclick="showSection('luythua')">🔢 Lũy thừa</button>
        <button onclick="showSection('tile')">📐 Tỉ lệ thức</button>
        <button onclick="showSection('thuan')">📈 Tỉ lệ thuận</button>
        <button onclick="showSection('nghich')">📉 Tỉ lệ nghịch</button>
        <button onclick="showSection('bieuthuc')">🧮 Biểu thức</button>
        <button onclick="showSection('donthuc')">✏️ Đơn thức</button>
        <button onclick="showSection('dathuc')">📊 Đa thức</button>
        <button onclick="showSection('pt')">❓ Phương trình</button>
        <button onclick="showSection('thongke')">📋 Thống kê</button>
    </div>


    <!-- PHÂN SỐ -->
    <div id="phanso" class="section active">
        <div class="card">
            <h2>➗ Tính toán phân số</h2>
            <p>Nhập hai phân số a/b và c/d.</p>

            <input id="a" type="number" placeholder="Tử số a">
            <input id="b" type="number" placeholder="Mẫu số b">

            <input id="c" type="number" placeholder="Tử số c">
            <input id="d" type="number" placeholder="Mẫu số d">

            <button class="calculate" onclick="phanSo()">TÍNH KẾT QUẢ</button>

            <div id="rsPhanSo" class="result"></div>
        </div>
    </div>


    <!-- LŨY THỪA -->
    <div id="luythua" class="section">
        <div class="card">
            <h2>🔢 Lũy thừa</h2>

            <input id="base" type="number" placeholder="Nhập cơ số a">
            <input id="expo" type="number" placeholder="Nhập số mũ n">

            <button class="calculate" onclick="luyThua()">TÍNH LŨY THỪA</button>

            <div id="rsLuyThua" class="result"></div>
        </div>
    </div>


    <!-- TỈ LỆ THỨC -->
    <div id="tile" class="section">
        <div class="card">
            <h2>📐 Tỉ lệ thức</h2>

            <p>a / b = x / d</p>

            <input id="ta" type="number" placeholder="a">
            <input id="tb" type="number" placeholder="b">
            <input id="td" type="number" placeholder="d">

            <button class="calculate" onclick="tiLe()">TÌM X</button>

            <div id="rsTiLe" class="result"></div>
        </div>
    </div>


    <!-- TỈ LỆ THUẬN -->
    <div id="thuan" class="section">
        <div class="card">
            <h2>📈 Đại lượng tỉ lệ thuận</h2>

            <p>y₁ / x₁ = y₂ / x₂</p>

            <input id="x1" type="number" placeholder="x₁">
            <input id="y1" type="number" placeholder="y₁">
            <input id="x2" type="number" placeholder="x₂">

            <button class="calculate" onclick="tiLeThuan()">TÌM y₂</button>

            <div id="rsThuan" class="result"></div>
        </div>
    </div>


    <!-- TỈ LỆ NGHỊCH -->
    <div id="nghich" class="section">
        <div class="card">
            <h2>📉 Đại lượng tỉ lệ nghịch</h2>

            <p>x₁ × y₁ = x₂ × y₂</p>

            <input id="nx1" type="number" placeholder="x₁">
            <input id="ny1" type="number" placeholder="y₁">
            <input id="nx2" type="number" placeholder="x₂">

            <button class="calculate" onclick="tiLeNghich()">TÌM y₂</button>

            <div id="rsNghich" class="result"></div>
        </div>
    </div>


    <!-- BIỂU THỨC -->
    <div id="bieuthuc" class="section">
        <div class="card">
            <h2>🧮 Biểu thức đại số</h2>

            <p>A = 2x² + 3x - 5</p>

            <input id="bx" type="number" placeholder="Nhập x">

            <button class="calculate" onclick="bieuThuc()">TÍNH A</button>

            <div id="rsBieuThuc" class="result"></div>
        </div>
    </div>


    <!-- ĐƠN THỨC -->
    <div id="donthuc" class="section">
        <div class="card">
            <h2>✏️ Đơn thức</h2>

            <p>A = a × xⁿ</p>

            <input id="da" type="number" placeholder="a">
            <input id="dx" type="number" placeholder="x">
            <input id="dn" type="number" placeholder="n">

            <button class="calculate" onclick="donThuc()">TÍNH A</button>

            <div id="rsDonThuc" class="result"></div>
        </div>
    </div>


    <!-- ĐA THỨC -->
    <div id="dathuc" class="section">
        <div class="card">
            <h2>📊 Đa thức</h2>

            <p>P(x) = ax² + bx + c</p>

            <input id="pa" type="number" placeholder="a">
            <input id="pb" type="number" placeholder="b">
            <input id="pc" type="number" placeholder="c">
            <input id="px" type="number" placeholder="x">

            <button class="calculate" onclick="daThuc()">TÍNH P(x)</button>

            <div id="rsDaThuc" class="result"></div>
        </div>
    </div>


    <!-- PHƯƠNG TRÌNH -->
    <div id="pt" class="section">
        <div class="card">
            <h2>❓ Phương trình bậc nhất</h2>

            <p>ax + b = 0</p>

            <input id="qa" type="number" placeholder="a">
            <input id="qb" type="number" placeholder="b">

            <button class="calculate" onclick="phuongTrinh()">GIẢI PHƯƠNG TRÌNH</button>

            <div id="rsPT" class="result"></div>
        </div>
    </div>


    <!-- THỐNG KÊ -->
    <div id="thongke" class="section">
        <div class="card">
            <h2>📋 Thống kê</h2>

            <p>Nhập các số, cách nhau bằng dấu phẩy.</p>

            <input id="numbers" type="text" placeholder="Ví dụ: 5, 7, 8, 10, 12">

            <button class="calculate" onclick="thongKe()">THỐNG KÊ</button>

            <div id="rsThongKe" class="result"></div>
        </div>
    </div>

</div>

<footer>
    <p>🎓 Toán Đại Số 7 • Học tập vui vẻ • Luyện tập mỗi ngày</p>
</footer>


<script>

/* MENU */
function showSection(id) {

    let sections = document.querySelectorAll(".section");

    sections.forEach(function(section) {
        section.classList.remove("active");
    });

    document.getElementById(id).classList.add("active");

    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });
}


/* PHÂN SỐ */
function phanSo() {

    let a = Number(document.getElementById("a").value);
    let b = Number(document.getElementById("b").value);
    let c = Number(document.getElementById("c").value);
    let d = Number(document.getElementById("d").value);

    if (b === 0 || d === 0) {
        document.getElementById("rsPhanSo").innerHTML =
            "⚠️ Mẫu số không được bằng 0!";
        return;
    }

    let tong = (a*d + b*c)/(b*d);
    let hieu = (a*d - b*c)/(b*d);
    let tich = (a*c)/(b*d);

    if (c === 0) {
        document.getElementById("rsPhanSo").innerHTML =
            `Tổng = ${tong}<br>
             Hiệu = ${hieu}<br>
             Tích = ${tich}<br>
             ⚠️ Không thể chia cho 0.`;
        return;
    }

    let thuong = (a*d)/(b*c);

    document.getElementById("rsPhanSo").innerHTML =
        `➕ Tổng = ${tong}<br>
         ➖ Hiệu = ${hieu}<br>
         ✖️ Tích = ${tich}<br>
         ➗ Thương = ${thuong}`;
}


/* LŨY THỪA */
function luyThua() {

    let a = Number(document.getElementById("base").value);
    let n = Number(document.getElementById("expo").value);

    let kq = Math.pow(a,n);

    document.getElementById("rsLuyThua").innerHTML =
        `🎯 ${a}<sup>${n}</sup> = <b>${kq}</b>`;
}


/* TỈ LỆ THỨC */
function tiLe() {

    let a = Number(document.getElementById("ta").value);
    let b = Number(document.getElementById("tb").value);
    let d = Number(document.getElementById("td").value);

    if (b === 0) {
        document.getElementById("rsTiLe").innerHTML =
            "⚠️ b không được bằng 0!";
        return;
    }

    let x = a*d/b;

    document.getElementById("rsTiLe").innerHTML =
        `🎯 x = ${x}`;
}


/* TỈ LỆ THUẬN */
function tiLeThuan() {

    let x1 = Number(document.getElementById("x1").value);
    let y1 = Number(document.getElementById("y1").value);
    let x2 = Number(document.getElementById("x2").value);

    if (x1 === 0) {
        document.getElementById("rsThuan").innerHTML =
            "⚠️ x₁ không được bằng 0!";
        return;
    }

    let y2 = y1*x2/x1;

    document.getElementById("rsThuan").innerHTML =
        `🎯 y₂ = ${y2}`;
}


/* TỈ LỆ NGHỊCH */
function tiLeNghich() {

    let x1 = Number(document.getElementById("nx1").value);
    let y1 = Number(document.getElementById("ny1").value);
    let x2 = Number(document.getElementById("nx2").value);

    if (x2 === 0) {
        document.getElementById("rsNghich").innerHTML =
            "⚠️ x₂ không được bằng 0!";
        return;
    }

    let y2 = x1*y1/x2;

    document.getElementById("rsNghich").innerHTML =
        `🎯 y₂ = ${y2}`;
}


/* BIỂU THỨC */
function bieuThuc() {

    let x = Number(document.getElementById("bx").value);

    let A = 2*x*x + 3*x - 5;

    document.getElementById("rsBieuThuc").innerHTML =
        `🎯 A = ${A}`;
}


/* ĐƠN THỨC */
function donThuc() {

    let a = Number(document.getElementById("da").value);
    let x = Number(document.getElementById("dx").value);
    let n = Number(document.getElementById("dn").value);

    let A = a*Math.pow(x,n);

    document.getElementById("rsDonThuc").innerHTML =
        `🎯 A = ${A}`;
}


/* ĐA THỨC */
function daThuc() {

    let a = Number(document.getElementById("pa").value);
    let b = Number(document.getElementById("pb").value);
    let c = Number(document.getElementById("pc").value);
    let x = Number(document.getElementById("px").value);

    let P = a*x*x + b*x + c;

    document.getElementById("rsDaThuc").innerHTML =
        `🎯 P(${x}) = ${P}`;
}


/* PHƯƠNG TRÌNH */
function phuongTrinh() {

    let a = Number(document.getElementById("qa").value);
    let b = Number(document.getElementById("qb").value);

    if (a === 0) {

        if (b === 0) {
            document.getElementById("rsPT").innerHTML =
                "♾️ Phương trình có vô số nghiệm.";
        } else {
            document.getElementById("rsPT").innerHTML =
                "❌ Phương trình vô nghiệm.";
        }

        return;
    }

    let x = -b/a;

    document.getElementById("rsPT").innerHTML =
        `🎯 Nghiệm: x = ${x}`;
}


/* THỐNG KÊ */
function thongKe() {

    let text = document.getElementById("numbers").value;

    let arr = text.split(",")
                  .map(Number)
                  .filter(x => !isNaN(x));

    if (arr.length === 0) {
        document.getElementById("rsThongKe").innerHTML =
            "⚠️ Hãy nhập dữ liệu!";
        return;
    }

    let tong = arr.reduce((a,b) => a+b, 0);
    let tb = tong / arr.length;

    let max = Math.max(...arr);
    let min = Math.min(...arr);

    document.getElementById("rsThongKe").innerHTML =
        `📊 Số lượng: ${arr.length}<br>
         ➕ Tổng: ${tong}<br>
         📈 Trung bình: ${tb}<br>
         🔺 Lớn nhất: ${max}<br>
         🔻 Nhỏ nhất: ${min}`;
}

</script>

</body>
</html>
