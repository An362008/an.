<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Toán Đại Số 7 - Học, Tính toán & Bài tập</title>
<style>
*{box-sizing:border-box}
body{margin:0;font-family:Arial,Helvetica,sans-serif;background:linear-gradient(135deg,#6c63ff,#00c6ff,#7bed9f);background-size:300% 300%;animation:bg 12s ease infinite;color:#172033;min-height:100vh}
@keyframes bg{0%,100%{background-position:0 50%}50%{background-position:100% 50%}}
header{padding:34px 20px;text-align:center;color:white}
header h1{font-size:clamp(32px,6vw,58px);margin:0 0 8px;text-shadow:0 5px 15px #0005}
header p{font-size:18px;margin:0}
nav{position:sticky;top:0;z-index:20;background:#ffffffdd;backdrop-filter:blur(12px);box-shadow:0 5px 20px #0002;display:flex;justify-content:center;gap:10px;padding:12px;flex-wrap:wrap}
nav button,.btn{border:0;border-radius:14px;padding:12px 18px;font-weight:700;cursor:pointer;transition:.2s}
nav button{background:#eef1ff;color:#4b43c6}
nav button:hover,.btn:hover{transform:translateY(-3px);box-shadow:0 8px 18px #0002}
.container{max-width:1150px;margin:25px auto;padding:0 16px}
.page{display:none}.page.active{display:block}
.hero,.panel,.topic,.question,.score{background:#fffffff2;border-radius:24px;box-shadow:0 12px 35px #0002}
.hero{padding:35px;text-align:center}
.hero h2{font-size:34px;margin:0 0 12px;color:#5148d8}
.cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:18px;margin-top:25px}
.topic{padding:24px;cursor:pointer;transition:.25s;border:3px solid transparent}
.topic:hover{transform:translateY(-7px) rotate(.5deg);border-color:#7c72ff}
.topic .icon{font-size:45px}.topic h3{margin:10px 0 7px}.topic p{color:#586174}
.panel{padding:28px;margin-bottom:20px}
.panel h2{color:#5148d8;margin-top:0}
.subnav{display:flex;flex-wrap:wrap;gap:9px;margin-bottom:20px}
.subnav button{background:#f0f2ff;color:#4c45bb;border:2px solid #dfe2ff;border-radius:12px;padding:10px 13px;font-weight:700;cursor:pointer}
.lesson{display:none}.lesson.active{display:block}
.lesson h3{font-size:25px;color:#3f38a8}.formula{background:#f2f8ff;border-left:5px solid #00a8ff;padding:14px;border-radius:12px;font-size:20px;margin:12px 0}
.example{background:#f7fff4;border-left:5px solid #2ed573;padding:14px;border-radius:12px}
label{display:block;font-weight:700;margin-top:10px}input,select{width:100%;padding:12px;border:2px solid #dfe3ef;border-radius:12px;font-size:16px;margin-top:6px}
.btn{background:linear-gradient(135deg,#6258e8,#00a8ff);color:white;margin-top:14px}
.result{margin-top:15px;padding:15px;border-radius:14px;background:#ecfff5;border-left:5px solid #20bf6b;line-height:1.7}
.question{padding:20px;margin:15px 0;border-left:6px solid #6c63ff}
.question h3{margin-top:0}.options label{font-weight:400;background:#f7f8ff;padding:11px;border-radius:10px;margin:8px 0;cursor:pointer}.options label:hover{background:#e9ebff}
.topic-filter{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:15px}.topic-filter button{border:0;background:#eeeefd;padding:9px 13px;border-radius:12px;cursor:pointer;font-weight:700}
.quiz-head{display:flex;justify-content:space-between;gap:15px;align-items:center;flex-wrap:wrap;background:#fff;padding:16px;border-radius:18px;margin-bottom:15px}
.badge{padding:9px 13px;background:#fff2a8;border-radius:12px;font-weight:800}
#quizArea{display:none}
#quizArea.show{display:block}
.progress{height:12px;background:#e8eaf2;border-radius:20px;overflow:hidden}.progress span{display:block;height:100%;background:linear-gradient(90deg,#ff6b6b,#ffd32a,#20bf6b);width:0;transition:.3s}
.score{text-align:center;padding:30px;display:none}.score.show{display:block}
.score .big{font-size:52px;font-weight:900;color:#5148d8}
footer{text-align:center;color:white;padding:25px}
.small{color:#667085;font-size:14px}
@media(max-width:650px){.hero,.panel{padding:20px}.quiz-head{display:block}.quiz-head>*{margin:5px 0}}
</style>
</head>
<body>
<header>
  <h1>📚 TOÁN ĐẠI SỐ 7</h1>
  <p>Học lý thuyết • Tính toán • Luyện bài tập • Tính điểm tự động</p>
</header>

<nav>
  <button onclick="showPage('home')">🏠 Trang chủ</button>
  <button onclick="showPage('theory')">📖 Lý thuyết</button>
  <button onclick="showPage('calc')">🧮 Tính toán</button>
  <button onclick="showPage('practice')">📝 Bài tập</button>
</nav>

<main class="container">

<section id="home" class="page active">
  <div class="hero">
    <h2>🌟 Chào mừng đến với Toán Đại Số 7!</h2>
    <p>Chọn một khu vực để bắt đầu học.</p>
    <div class="cards">
      <div class="topic" onclick="showPage('theory')"><div class="icon">📖</div><h3>LÝ THUYẾT</h3><p>Chia thành từng chuyên đề, học theo từng phần.</p></div>
      <div class="topic" onclick="showPage('calc')"><div class="icon">🧮</div><h3>TÍNH TOÁN</h3><p>Mỗi chuyên đề có công cụ tính riêng.</p></div>
      <div class="topic" onclick="showPage('practice')"><div class="icon">📝</div><h3>BÀI TẬP</h3><p>Nhiều phần, nhiều câu hỏi và chấm điểm tự động.</p></div>
    </div>
  </div>
</section>

<section id="theory" class="page">
<div class="panel">
<h2>📖 Lý thuyết Toán 7</h2>
<div class="subnav">
<button onclick="lesson('lt1')">🔢 Số hữu tỉ</button>
<button onclick="lesson('lt2')">⚡ Lũy thừa</button>
<button onclick="lesson('lt3')">📐 Tỉ lệ thức</button>
<button onclick="lesson('lt4')">📈 Tỉ lệ thuận</button>
<button onclick="lesson('lt5')">📉 Tỉ lệ nghịch</button>
<button onclick="lesson('lt6')">🧮 Biểu thức</button>
<button onclick="lesson('lt7')">✏️ Đơn thức</button>
<button onclick="lesson('lt8')">📊 Đa thức</button>
<button onclick="lesson('lt9')">🎯 Nghiệm đa thức</button>
<button onclick="lesson('lt10')">📋 Thống kê</button>
</div>

<div id="lt1" class="lesson active"><h3>🔢 Số hữu tỉ</h3><p>Số hữu tỉ là số viết được dưới dạng a/b, trong đó a,b là số nguyên và b khác 0.</p><div class="formula">a/b + c/d = (ad + bc)/bd</div><div class="formula">a/b × c/d = ac/bd</div><div class="example">Ví dụ: 1/2 + 1/3 = 5/6.</div></div>
<div id="lt2" class="lesson"><h3>⚡ Lũy thừa</h3><p>Lũy thừa biểu thị phép nhân một số với chính nó nhiều lần.</p><div class="formula">aᵐ × aⁿ = aᵐ⁺ⁿ</div><div class="formula">aᵐ : aⁿ = aᵐ⁻ⁿ (a ≠ 0)</div></div>
<div id="lt3" class="lesson"><h3>📐 Tỉ lệ thức</h3><p>Tỉ lệ thức là một đẳng thức của hai tỉ số.</p><div class="formula">a/b = c/d ⇒ ad = bc</div><div class="example">Có thể dùng tính chất này để tìm số chưa biết.</div></div>
<div id="lt4" class="lesson"><h3>📈 Đại lượng tỉ lệ thuận</h3><p>Nếu y = kx thì y tỉ lệ thuận với x theo hệ số k.</p><div class="formula">y/x = k</div></div>
<div id="lt5" class="lesson"><h3>📉 Đại lượng tỉ lệ nghịch</h3><p>Nếu y = a/x với a khác 0 thì y tỉ lệ nghịch với x.</p><div class="formula">x × y = a</div></div>
<div id="lt6" class="lesson"><h3>🧮 Biểu thức đại số</h3><p>Biểu thức đại số gồm số, biến và các phép toán.</p><div class="example">Ví dụ: A = 2x² + 3x - 5.</div></div>
<div id="lt7" class="lesson"><h3>✏️ Đơn thức</h3><p>Đơn thức là biểu thức đại số chỉ gồm một số, một biến hoặc tích của số và biến.</p><div class="example">Ví dụ: 3x²y là một đơn thức.</div></div>
<div id="lt8" class="lesson"><h3>📊 Đa thức</h3><p>Đa thức là tổng của những đơn thức.</p><div class="example">Ví dụ: P(x) = 2x² + 3x - 5.</div></div>
<div id="lt9" class="lesson"><h3>🎯 Nghiệm của đa thức</h3><p>Số a là nghiệm của P(x) nếu P(a) = 0.</p><div class="formula">P(a) = 0 ⇒ a là nghiệm của P(x)</div></div>
<div id="lt10" class="lesson"><h3>📋 Thống kê</h3><p>Dữ liệu có thể được thu thập, phân loại và biểu diễn bằng bảng hoặc biểu đồ. Trung bình cộng bằng tổng các giá trị chia cho số giá trị.</p></div>
</div>
</section>

<section id="calc" class="page">
<div class="panel">
<h2>🧮 Tính toán theo từng phần</h2>
<div class="subnav">
<button onclick="calc('c1')">➗ Phân số</button>
<button onclick="calc('c2')">⚡ Lũy thừa</button>
<button onclick="calc('c3')">📐 Tỉ lệ thức</button>
<button onclick="calc('c4')">📈 Tỉ lệ thuận</button>
<button onclick="calc('c5')">📉 Tỉ lệ nghịch</button>
<button onclick="calc('c6')">🧮 Biểu thức</button>
<button onclick="calc('c7')">✏️ Đơn thức</button>
<button onclick="calc('c8')">📊 Đa thức</button>
<button onclick="calc('c9')">🎯 Phương trình</button>
<button onclick="calc('c10')">📋 Thống kê</button>
</div>

<div id="c1" class="lesson active"><h3>➗ Tính phân số</h3><input id="a" type="number" placeholder="Tử số a"><input id="b" type="number" placeholder="Mẫu số b"><input id="c" type="number" placeholder="Tử số c"><input id="d" type="number" placeholder="Mẫu số d"><button class="btn" onclick="fraction()">✨ Tính</button><div id="r1" class="result"></div></div>
<div id="c2" class="lesson"><h3>⚡ Tính lũy thừa</h3><input id="base" type="number" placeholder="Cơ số a"><input id="exp" type="number" placeholder="Số mũ n"><button class="btn" onclick="power()">✨ Tính</button><div id="r2" class="result"></div></div>
<div id="c3" class="lesson"><h3>📐 Tìm x trong a/b = x/d</h3><input id="ta" type="number" placeholder="a"><input id="tb" type="number" placeholder="b"><input id="td" type="number" placeholder="d"><button class="btn" onclick="ratio()">✨ Tìm x</button><div id="r3" class="result"></div></div>
<div id="c4" class="lesson"><h3>📈 Tỉ lệ thuận</h3><input id="tx1" type="number" placeholder="x₁"><input id="ty1" type="number" placeholder="y₁"><input id="tx2" type="number" placeholder="x₂"><button class="btn" onclick="direct()">✨ Tìm y₂</button><div id="r4" class="result"></div></div>
<div id="c5" class="lesson"><h3>📉 Tỉ lệ nghịch</h3><input id="ix1" type="number" placeholder="x₁"><input id="iy1" type="number" placeholder="y₁"><input id="ix2" type="number" placeholder="x₂"><button class="btn" onclick="inverse()">✨ Tìm y₂</button><div id="r5" class="result"></div></div>
<div id="c6" class="lesson"><h3>🧮 A = 2x² + 3x - 5</h3><input id="bx" type="number" placeholder="Nhập x"><button class="btn" onclick="expr()">✨ Tính A</button><div id="r6" class="result"></div></div>
<div id="c7" class="lesson"><h3>✏️ A = a × xⁿ</h3><input id="da" type="number" placeholder="a"><input id="dx" type="number" placeholder="x"><input id="dn" type="number" placeholder="n"><button class="btn" onclick="mono()">✨ Tính A</button><div id="r7" class="result"></div></div>
<div id="c8" class="lesson"><h3>📊 P(x) = ax² + bx + c</h3><input id="pa" type="number" placeholder="a"><input id="pb" type="number" placeholder="b"><input id="pc" type="number" placeholder="c"><input id="px" type="number" placeholder="x"><button class="btn" onclick="poly()">✨ Tính P(x)</button><div id="r8" class="result"></div></div>
<div id="c9" class="lesson"><h3>🎯 Giải ax + b = 0</h3><input id="qa" type="number" placeholder="a"><input id="qb" type="number" placeholder="b"><button class="btn" onclick="equation()">✨ Giải</button><div id="r9" class="result"></div></div>
<div id="c10" class="lesson"><h3>📋 Thống kê</h3><input id="nums" placeholder="Ví dụ: 5, 7, 8, 10, 12"><button class="btn" onclick="stats()">✨ Thống kê</button><div id="r10" class="result"></div></div>
</div>
</section>

<section id="practice" class="page">
<div class="panel">
<h2>📝 Bài tập nhiều phần - tính điểm tự động</h2>
<p class="small">Mỗi đề có nhiều chuyên đề. Mỗi câu đúng được 1 điểm. Điểm cuối = số câu đúng / tổng số câu × 10.</p>
<div class="topic-filter">
<button onclick="startQuiz('all')">🌟 Tổng hợp</button>
<button onclick="startQuiz('fraction')">➗ Số hữu tỉ</button>
<button onclick="startQuiz('power')">⚡ Lũy thừa</button>
<button onclick="startQuiz('ratio')">📐 Tỉ lệ thức</button>
<button onclick="startQuiz('algebra')">🧮 Đại số</button>
<button onclick="startQuiz('stats')">📋 Thống kê</button>
</div>
<div id="quizArea">
<div class="quiz-head"><div><b id="quizTitle">Đề bài</b><br><span id="count"></span></div><div class="badge">🏆 Điểm: <span id="liveScore">0</span></div></div>
<div class="progress"><span id="bar"></span></div>
<form id="quizForm"></form>
<button class="btn" onclick="submitQuiz()">🎯 NỘP BÀI & TÍNH ĐIỂM</button>
<div id="scoreBox" class="score"></div>
</div>
</div>
</section>

</main>
<footer>🎓 Toán Đại Số 7 • Học vui - Luyện giỏi • Chạy trực tiếp trên trình duyệt</footer>

<script>
function showPage(id){document.querySelectorAll('.page').forEach(x=>x.classList.remove('active'));document.getElementById(id).classList.add('active');scrollTo({top:0,behavior:'smooth'})}
function lesson(id){document.querySelectorAll('#theory .lesson').forEach(x=>x.classList.remove('active'));document.getElementById(id).classList.add('active')}
function calc(id){document.querySelectorAll('#calc .lesson').forEach(x=>x.classList.remove('active'));document.getElementById(id).classList.add('active')}
const n=id=>Number(document.getElementById(id).value);
function fraction(){let a=n('a'),b=n('b'),c=n('c'),d=n('d');let r=document.getElementById('r1');if(!b||!d){r.innerHTML='⚠️ Mẫu số phải khác 0';return}r.innerHTML=`➕ Tổng: ${(a*d+b*c)/(b*d)}<br>➖ Hiệu: ${(a*d-b*c)/(b*d)}<br>✖️ Tích: ${(a*c)/(b*d)}<br>➗ Thương: ${c?((a*d)/(b*c)):'Không xác định'}`}
function power(){document.getElementById('r2').innerHTML=`🎯 Kết quả: <b>${Math.pow(n('base'),n('exp'))}</b>`}
function ratio(){let a=n('ta'),b=n('tb'),d=n('td');document.getElementById('r3').innerHTML=b?`🎯 x = <b>${a*d/b}</b>`:'⚠️ b phải khác 0'}
function direct(){let x1=n('tx1'),y1=n('ty1'),x2=n('tx2');document.getElementById('r4').innerHTML=x1?`🎯 y₂ = <b>${y1*x2/x1}</b>`:'⚠️ x₁ phải khác 0'}
function inverse(){let x1=n('ix1'),y1=n('iy1'),x2=n('ix2');document.getElementById('r5').innerHTML=x2?`🎯 y₂ = <b>${x1*y1/x2}</b>`:'⚠️ x₂ phải khác 0'}
function expr(){let x=n('bx');document.getElementById('r6').innerHTML=`🎯 A = <b>${2*x*x+3*x-5}</b>`}
function mono(){document.getElementById('r7').innerHTML=`🎯 A = <b>${n('da')*Math.pow(n('dx'),n('dn'))}</b>`}
function poly(){let a=n('pa'),b=n('pb'),c=n('pc'),x=n('px');document.getElementById('r8').innerHTML=`🎯 P(x) = <b>${a*x*x+b*x+c}</b>`}
function equation(){let a=n('qa'),b=n('qb'),r=document.getElementById('r9');if(a===0)r.innerHTML=b===0?'♾️ Vô số nghiệm':'❌ Vô nghiệm';else r.innerHTML=`🎯 x = <b>${-b/a}</b>`}
function stats(){let a=document.getElementById('nums').value.split(',').map(Number).filter(x=>!isNaN(x));let r=document.getElementById('r10');if(!a.length){r.innerHTML='⚠️ Chưa có dữ liệu';return}let s=a.reduce((x,y)=>x+y,0);r.innerHTML=`📊 Số lượng: ${a.length}<br>➕ Tổng: ${s}<br>📈 Trung bình: ${s/a.length}<br>🔺 Lớn nhất: ${Math.max(...a)}<br>🔻 Nhỏ nhất: ${Math.min(...a)}`}

const Q=[
{t:'fraction',q:'Tính 1/2 + 1/3 bằng bao nhiêu?',o:['5/6','2/5','1/6','3/5'],a:0},
{t:'fraction',q:'Tính 3/4 - 1/4 bằng bao nhiêu?',o:['1/2','1/4','2/3','3/8'],a:0},
{t:'fraction',q:'Tính 2/3 × 3/4 bằng bao nhiêu?',o:['1/2','2/7','5/12','3/8'],a:0},
{t:'power',q:'2³ bằng bao nhiêu?',o:['6','8','9','12'],a:1},
{t:'power',q:'3² × 3³ bằng bao nhiêu?',o:['3⁵','3⁶','9⁵','6⁵'],a:0},
{t:'power',q:'5⁰ bằng bao nhiêu?',o:['0','1','5','10'],a:1},
{t:'ratio',q:'Nếu a/b = c/d thì đẳng thức nào đúng?',o:['ab = cd','ad = bc','a+c = b+d','a/b = d/c'],a:1},
{t:'ratio',q:'2/3 = x/12. Giá trị x là?',o:['6','8','9','10'],a:1},
{t:'ratio',q:'3/5 = 12/x. Giá trị x là?',o:['15','18','20','25'],a:2},
{t:'algebra',q:'Với x = 2, A = 2x² + 3x - 5 bằng?',o:['5','7','9','11'],a:1},
{t:'algebra',q:'Đơn thức nào sau đây?',o:['2x²','x+2','x²-1','2/x'],a:0},
{t:'algebra',q:'Nếu P(x)=x-3 thì nghiệm của P là?',o:['-3','0','1','3'],a:3},
{t:'stats',q:'Trung bình cộng của 4, 6, 8 là?',o:['5','6','7','8'],a:1},
{t:'stats',q:'Số lớn nhất trong 3, 9, 5, 7 là?',o:['3','5','7','9'],a:3},
{t:'stats',q:'Dãy 2, 4, 6, 8 có bao nhiêu giá trị?',o:['2','3','4','5'],a:2}
];
let current=[],submitted=false;
function startQuiz(type){
 current=type==='all'?[...Q]:Q.filter(x=>x.t===type);
 submitted=false;
 document.getElementById('quizArea').classList.add('show');
 document.getElementById('scoreBox').classList.remove('show');
 document.getElementById('quizTitle').textContent=type==='all'?'🌟 Đề tổng hợp Toán Đại Số 7':'📝 Bài tập: '+({fraction:'Số hữu tỉ',power:'Lũy thừa',ratio:'Tỉ lệ thức',algebra:'Đại số',stats:'Thống kê'}[type]);
 document.getElementById('count').textContent=current.length+' câu hỏi';
 document.getElementById('liveScore').textContent='0';
 let f=document.getElementById('quizForm');f.innerHTML='';
 current.forEach((x,i)=>{let d=document.createElement('div');d.className='question';d.innerHTML=`<h3>Câu ${i+1}: ${x.q}</h3><div class="options">${x.o.map((o,j)=>`<label><input type="radio" name="q${i}" value="${j}"> ${String.fromCharCode(65+j)}. ${o}</label>`).join('')}</div>`;f.appendChild(d)});
 document.getElementById('bar').style.width='0%';
 window.scrollTo({top:document.getElementById('quizArea').offsetTop-80,behavior:'smooth'});
}
function submitQuiz(){
 if(submitted)return;
 let score=0,answered=0;
 current.forEach((x,i)=>{let el=document.querySelector(`input[name="q${i}"]:checked`);if(el){answered++;if(Number(el.value)===x.a)score++}});
 let point=(score/current.length*10);
 let box=document.getElementById('scoreBox');
 box.classList.add('show');
 box.innerHTML=`<div class="big">${point.toFixed(1)}/10</div><h2>🎉 Hoàn thành bài!</h2><p><b>${score}/${current.length}</b> câu đúng • Đã trả lời ${answered}/${current.length} câu</p><p>${point>=8?'🌟 Rất tốt!':point>=5?'👍 Cố gắng thêm nhé!':'💪 Hãy xem lại lý thuyết và làm lại!'}</p>`;
 document.getElementById('liveScore').textContent=score;
 document.getElementById('bar').style.width=(score/current.length*100)+'%';
 submitted=true;
}
</script>
</body>
</html>
