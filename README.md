# arackars-lastirmaa
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>OTOMOBİL KARŞILAŞTRIMA</title>
<meta name="description" content="Türkiye'nin en detaylı araç karşılaştırma ve teknik analiz platformu.">
<meta name="keywords" content="araç karşılaştırma, otomobil teknik özellikler, yakıt tüketimi karşılaştır">
<link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><rect width=%22100%22 height=%22100%22 rx=%2220%22 fill=%22%230056D2%22/><text x=%2250%%22 y=%2272%%22 text-anchor=%22middle%22 font-family=%22Arial%22 font-weight=%22900%22 font-size=%2265%22 fill=%22white%22>D</text></svg>">
    <style>
        :root {
            --primary: #00f2fe; --secondary: #4facfe; --accent: #f093fb;
            --dark-bg: #020617; --panel-bg: rgba(30, 41, 59, 0.7); --border: rgba(255, 255, 255, 0.1);
        }
        *{margin:0;padding:0;box-sizing:border-box;font-family: 'Inter', sans-serif;}
        body { background: radial-gradient(circle at top right, #1e293b, #020617); color: #f1f5f9; line-height: 1.5; }
        
        /* Navigasyon */
        nav { padding: 20px 5%; background: rgba(2, 6, 23, 0.9); backdrop-filter: blur(10px); border-bottom: 1px solid var(--border); position: sticky; top: 0; z-index: 1000; text-align: center; }
        .logo { font-size: 28px; font-weight: 900; background: linear-gradient(to right, var(--primary), var(--accent)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; letter-spacing: -1px; }

        main { max-width: 1200px; margin: 0 auto; padding: 20px; }

        /* Bilgi Kartları */
        .info-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin: 30px 0; }
        .info-card { background: var(--panel-bg); padding: 15px; border-radius: 12px; border-top: 3px solid var(--primary); font-size: 0.85rem; }
        .info-card h4 { color: var(--primary); margin-bottom: 5px; }

        /* Araç Seçim Alanı */
        .filter-section { background: var(--panel-bg); padding: 25px; border-radius: 20px; border: 1px solid var(--border); margin-bottom: 40px; text-align: center; }
        select { background: #0f172a; color: white; padding: 12px 20px; border-radius: 10px; border: 1px solid var(--secondary); margin: 5px; cursor: pointer; font-size: 1rem; }

        /* Araç Kartları */
        .cards-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 20px; }
        .car-card { background: var(--panel-bg); border-radius: 15px; overflow: hidden; border: 1px solid var(--border); transition: 0.4s; position: relative; }
        .car-card:hover { transform: translateY(-10px); border-color: var(--primary); box-shadow: 0 15px 30px rgba(0,0,0,0.5); }
        .car-img { width: 100%; height: 180px; object-fit: cover; filter: brightness(0.8); }
        .card-content { padding: 15px; }
        .card-content h3 { color: var(--primary); margin-bottom: 5px; }
        .btn-select { width: 100%; padding: 12px; background: var(--primary); border: none; font-weight: bold; cursor: pointer; color: #020617; transition: 0.3s; }
        .btn-select:hover { background: white; }

        /* Karşılaştırma Tablosu */
        .table-container { background: var(--panel-bg); border-radius: 20px; border: 1px solid var(--border); overflow-x: auto; margin-top: 40px; }
        table { width: 100%; border-collapse: collapse; min-width: 800px; }
        th, td { padding: 18px; text-align: left; border-bottom: 1px solid var(--border); }
        th { background: rgba(0,0,0,0.3); color: var(--accent); font-size: 0.8rem; text-transform: uppercase; }
        .label { font-weight: bold; color: #94a3b8; width: 25%; }

        /* Yorumlar ve Puanlama */
        .social-section { margin-top: 50px; display: grid; grid-template-columns: 1fr 1.5fr; gap: 30px; }
        .rating-box, .comment-box { background: var(--panel-bg); padding: 25px; border-radius: 20px; border: 1px solid var(--border); }
        .stars { font-size: 24px; color: #fbbf24; cursor: pointer; margin: 10px 0; }
        .comment-list { max-height: 300px; overflow-y: auto; margin-top: 15px; }
        .comment-item { background: rgba(0,0,0,0.2); padding: 10px; border-radius: 10px; margin-bottom: 10px; font-size: 0.9rem; border-left: 3px solid var(--accent); }
        input, textarea { width: 100%; padding: 12px; margin: 10px 0; background: #0f172a; border: 1px solid var(--border); color: white; border-radius: 8px; }

        footer { text-align: center; padding: 50px; opacity: 0.5; font-size: 0.8rem; border-top: 1px solid var(--border); margin-top: 50px; }

        @media (max-width: 768px) { .social-section { grid-template-columns: 1fr; } }
    </style>
</head>
<body>

<nav><div class="<div class="logo-wrapper" style="display: flex; align-items: center; gap: 12px; cursor: pointer;">
    <svg width="45" height="45" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <defs>
            <linearGradient id="grad" x1="0%" y1="0%" x2="100%" y2="100%">
                <stop offset="0%" style="stop-color:#00f2fe;stop-opacity:1" />
                <stop offset="100%" style="stop-color:#4facfe;stop-opacity:1" />
            </linearGradient>
        </defs>
        <rect width="100" height="100" rx="20" fill="#0056D2" />
        <text x="50%" y="72%" text-anchor="middle" font-family="Arial, sans-serif" font-weight="900" font-size="65" fill="white">D</text>
        <path d="M20 80 Q 50 20 90 40" stroke="#00f2fe" stroke-width="5" fill="none" stroke-linecap="round" />
    </svg>
    
    <div style="display: flex; flex-direction: column;">
        <span style="font-size: 22px; font-weight: 900; line-height: 1; background: linear-gradient(to right, #fff, #00f2fe); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">AUTOMATRIS</span>
        <span style="font-size: 10px; font-weight: bold; color: #4facfe; letter-spacing: 2px;">PRO ANALİZ</span>
    </div>
</div>ARAÇ KARŞILAŞTIRMA PLATFORMU</div></nav>

<main>
    <div class="info-grid">
        <div class="info-card"><h4>Motor & Performans</h4>HP hızı, Tork çekişi temsil eder. Continental Tires verileriyle optimize edilmiştir.</div>
        <div class="info-card"><h4>Şanzıman</h4>Güç aktarım merkezi. Vites türü (Otm/Man) sürüş karakterini belirler.</div>
        <div class="info-card"><h4>Güvenlik</h4>ABS, ESP ve Airbag sistemleri Otopratik standartlarında incelenmiştir.</div>
        <div class="info-card"><h4>Süspansiyon</h4>Yol tutuş ve konfor dengesi (McPherson, Çok Kollu vb.)</div>
    </div>

    <div class="filter-section">
        <h2>Segment Analizi Başlat</h2>
        <select id="segSelect" onchange="renderApp()">
            <option value="B">B Segmenti (10 Araç)</option>
            <option value="C">C Segmenti (10 Araç)</option>
            <option value="D">D Segmenti (10 Araç)</option>
        </select>
    </div>

    <div class="cards-grid" id="carGrid"></div>

    <div class="filter-section" style="margin-top:50px; border-color: var(--accent);">
        <h3>Teknik Karşılaştırma Matrisi</h3>
        <select id="sel1"></select> <span style="color:var(--primary); font-weight:bold;">VS</span> <select id="sel2"></select>
        <button onclick="updateTable()" class="btn-select" style="width:auto; padding: 10px 40px; border-radius:30px; margin-left:15px;">ANALİZ ET</button>
    </div>

    <div class="table-container">
        <table>
            <thead>
                <tr>
                    <th>Parametre</th>
                    <th id="name1" style="color:var(--primary)">Araç 1</th>
                    <th id="name2" style="color:var(--primary)">Araç 2</th>
                </tr>
            </thead>
            <tbody id="tableBody"></tbody>
        </table>
    </div>

    <div class="social-section">
        <div class="rating-box">
            <h3>Araç Puanla</h3>
            <p id="ratingTarget">Seçili Araç: -</p>
            <div class="stars" onclick="setRating(event)">★★★★★</div>
            <p id="ratingScore">Puan: 0 / 5</p>
            <button onclick="saveRating()" class="btn-select" style="border-radius:10px;">Puanı Gönder</button>
        </div>

        <div class="comment-box">
            <h3>Kullanıcı Yorumları</h3>
            <input type="text" id="userName" placeholder="Adınız">
            <textarea id="userComment" placeholder="Araç hakkındaki düşünceleriniz..."></textarea>
            <button onclick="addComment()" class="btn-select" style="border-radius:10px;">Yorum Yap</button>
            <div class="comment-list" id="commentList">
                <div class="comment-item"><b>Admin:</b> Veriler 2026 güncel kataloğuna aittir!</div>
            </div>
        </div>
    </div>
</main>

<footer>© 2026 Automatris PRO | Mühendislik ve Veri Analitiği Portalı</footer>

<script>
// 30 ARAÇLIK DEV VERİ SETİ
const db = {
    B: [
        { name: "VW Polo", brand: "VW", motor: "1.0 TSI 95HP", tork: "175 Nm", cons: "5.2L", size: "4074mm / 5 Kişi", safety: "6 Airbag + ESP", susp: "McPherson", trans: "7 İleri DSG", type: "Yarı Otomatik" },
        { name: "Renault Clio", brand: "Renault", motor: "1.0 TCe 90HP", tork: "160 Nm", cons: "5.0L", size: "4050mm / 5 Kişi", safety: "Şerit Takip", susp: "Torsiyon", trans: "X-Tronic", type: "Otomatik" },
        { name: "Toyota Yaris", brand: "Toyota", motor: "1.5 Hybrid 116HP", tork: "141 Nm", cons: "3.2L", size: "3940mm / 5 Kişi", safety: "Hybrid Safety", susp: "McPherson", trans: "e-CVT", type: "Otomatik" },
        { name: "Peugeot 208", brand: "Peugeot", motor: "1.2 PureTech 100HP", tork: "205 Nm", cons: "5.4L", size: "4055mm / 5 Kişi", safety: "i-Cockpit Safety", susp: "Yumuşak", trans: "EAT8", type: "Tam Otomatik" },
        { name: "Hyundai i20", brand: "Hyundai", motor: "1.4 MPI 100HP", tork: "134 Nm", cons: "6.1L", size: "4040mm / 5 Kişi", safety: "6 Airbag", susp: "Standart", trans: "6 İleri", type: "Tam Otomatik" },
        { name: "Ford Fiesta", brand: "Ford", motor: "1.0 EcoBoost 125HP", tork: "170 Nm", cons: "5.1L", size: "4040mm / 5 Kişi", safety: "Dinamik ESP", susp: "Spor", trans: "7 İleri", type: "Otomatik" },
        { name: "Skoda Fabia", brand: "Skoda", motor: "1.0 TSI 110HP", tork: "200 Nm", cons: "4.9L", size: "4108mm / 5 Kişi", safety: "Front Assist", susp: "Konfor", trans: "7 İleri DSG", type: "Yarı Otomatik" },
        { name: "Honda Jazz", brand: "Honda", motor: "1.5 i-MMD 109HP", tork: "253 Nm", cons: "3.5L", size: "4044mm / 5 Kişi", safety: "Honda Sensing", susp: "Yumuşak", trans: "e-CVT", type: "Otomatik" },
        { name: "Dacia Sandero", brand: "Renault", motor: "1.0 Turbo 90HP", tork: "160 Nm", cons: "5.3L", size: "4088mm / 5 Kişi", safety: "Temel Güvenlik", susp: "Sert Torsiyon", trans: "CVT", type: "Otomatik" },
        { name: "Opel Corsa", brand: "Opel", motor: "1.2 Turbo 100HP", tork: "205 Nm", cons: "5.3L", size: "4060mm / 5 Kişi", safety: "Tabela Tanıma", susp: "Alman Standart", trans: "8 İleri", type: "Tam Otomatik" }
    ],
    C: [
        { name: "VW Golf 8", brand: "VW", motor: "1.5 eTSI 150HP", tork: "250 Nm", cons: "5.8L", size: "4284mm / 5 Kişi", safety: "IQ.Drive", susp: "Bağımsız Arka", trans: "7 İleri DSG", type: "Yarı Otomatik" },
        { name: "Honda Civic", brand: "Honda", motor: "1.5 VTEC 182HP", tork: "240 Nm", cons: "6.3L", size: "4674mm / 5 Kişi", safety: "Sensing 2.0", susp: "Multi-link", trans: "CVT", type: "Otomatik" },
        { name: "Toyota Corolla", brand: "Toyota", motor: "1.8 Hybrid 140HP", tork: "185 Nm", cons: "4.5L", size: "4630mm / 5 Kişi", safety: "TSS 3.0", susp: "Çift Salıncak", trans: "e-CVT", type: "Otomatik" },
        { name: "Peugeot 308", brand: "Peugeot", motor: "1.2 PureTech 130HP", tork: "230 Nm", cons: "5.6L", size: "4367mm / 5 Kişi", safety: "360 Cam", susp: "Konfor", trans: "EAT8", type: "Tam Otomatik" },
        { name: "Skoda Octavia", brand: "Skoda", motor: "1.5 TSI 150HP", tork: "250 Nm", cons: "5.5L", size: "4689mm / 5 Kişi", safety: "9 Airbag", susp: "Adaptif", trans: "7 İleri DSG", type: "Yarı Otomatik" },
        { name: "Audi A3", brand: "Audi", motor: "1.5 TFSI 150HP", tork: "250 Nm", cons: "5.4L", size: "4343mm / 5 Kişi", safety: "Pre-Sense", susp: "Spor Bağımsız", trans: "S-Tronic", type: "Yarı Otomatik" },
        { name: "Renault Megane", brand: "Renault", motor: "1.3 TCe 140HP", tork: "240 Nm", cons: "5.9L", size: "4632mm / 5 Kişi", safety: "Visio System", susp: "Standart", trans: "7 İleri EDC", type: "Yarı Otomatik" },
        { name: "Ford Focus", brand: "Ford", motor: "1.5 Diesel 120HP", tork: "300 Nm", cons: "4.8L", size: "4378mm / 5 Kişi", safety: "Co-Pilot 360", susp: "Bağımsız", trans: "8 İleri", type: "Tam Otomatik" },
        { name: "Hyundai Elantra", brand: "Hyundai", motor: "1.6 MPI 123HP", tork: "154 Nm", cons: "6.4L", size: "4650mm / 5 Kişi", safety: "SmartSense", susp: "McPherson", trans: "IVT", type: "Otomatik" },
        { name: "Opel Astra", brand: "Opel", motor: "1.2 Turbo 130HP", tork: "230 Nm", cons: "5.5L", size: "4374mm / 5 Kişi", safety: "Intelli-Lux", susp: "Dinamik", trans: "8 İleri", type: "Tam Otomatik" }
    ],
    D: [
        { name: "Mercedes C200", brand: "Mercedes", motor: "1.5 204HP", tork: "300 Nm", cons: "6.8L", size: "4751mm / 5 Kişi", safety: "Distronic", susp: "Çok Kollu Havalı", trans: "9G-Tronic", type: "Tam Otomatik" },
        { name: "BMW 320i", brand: "BMW", motor: "1.6 170HP", tork: "250 Nm", cons: "7.2L", size: "4713mm / 5 Kişi", safety: "Active Guard", susp: "M Sport", trans: "8 İleri ZF", type: "Tam Otomatik" },
        { name: "Audi A4", brand: "Audi", motor: "2.0 TFSI 204HP", tork: "320 Nm", cons: "6.5L", size: "4762mm / 5 Kişi", safety: "Quattro", susp: "5 Kollu", trans: "S-Tronic", type: "Yarı Otomatik" },
        { name: "VW Passat", brand: "VW", motor: "1.5 eTSI 150HP", tork: "250 Nm", cons: "5.8L", size: "4917mm / 5 Kişi", safety: "Travel Assist", susp: "DCC Adaptif", trans: "7 İleri DSG", type: "Yarı Otomatik" },
        { name: "Skoda Superb", brand: "Skoda", motor: "2.0 TDI 193HP", tork: "400 Nm", cons: "5.5L", size: "4912mm / 5 Kişi", safety: "Crew Protect", susp: "DCC+", trans: "7 İleri DSG", type: "Yarı Otomatik" },
        { name: "Volvo S60", brand: "Volvo", motor: "2.0 B5 250HP", tork: "350 Nm", cons: "6.7L", size: "4761mm / 5 Kişi", safety: "City Safety", susp: "Dinamik", trans: "8 İleri", type: "Tam Otomatik" },
        { name: "Peugeot 508", brand: "Peugeot", motor: "1.5 Diesel 130HP", tork: "300 Nm", cons: "4.5L", size: "4750mm / 5 Kişi", safety: "Night Vision", susp: "Aktif", trans: "EAT8", type: "Tam Otomatik" },
        { name: "Toyota Camry", brand: "Toyota", motor: "2.5 Hybrid 218HP", tork: "221 Nm", cons: "4.4L", size: "4885mm / 5 Kişi", safety: "Safety Sense 2.5", susp: "Konfor Bağımsız", trans: "e-CVT", type: "Otomatik" },
        { name: "BMW 520d", brand: "BMW", motor: "2.0 Diesel 197HP", tork: "400 Nm", cons: "5.6L", size: "5060mm / 5 Kişi", safety: "Driving Assistant", susp: "Havalı Arka", trans: "Steptronic", type: "Tam Otomatik" },
        { name: "Alfa Giulia", brand: "Alfa Romeo", motor: "2.0 Turbo 280HP", tork: "400 Nm", cons: "7.4L", size: "4643mm / 5 Kişi", safety: "Integrated Brake", susp: "Alfa Link", trans: "8 İleri ZF", type: "Tam Otomatik" }
    ]
};

let currentRating = 0;

function renderApp() {
    const s = document.getElementById('segSelect').value;
    const grid = document.getElementById('carGrid');
    const s1 = document.getElementById('sel1');
    const s2 = document.getElementById('sel2');
    
    grid.innerHTML = ""; s1.innerHTML = ""; s2.innerHTML = "";
    
    db[s].forEach((c, i) => {
        grid.innerHTML += `
            <div class="car-card">
                <img src="https://placehold.co/400x250/0f172a/00f2fe?text=${c.name}" class="car-img">
                <div class="card-content">
                    <h3>${c.name}</h3>
                    <p style="font-size:0.8rem; color:#94a3b8">${c.motor} | ${c.type}</p>
                </div>
                <button class="btn-select" onclick="selectForCompare(${i})">SEÇ VE ANALİZ ET</button>
            </div>
        `;
        s1.add(new Option(c.name, i));
        s2.add(new Option(c.name, i));
    });
    s2.selectedIndex = 1;
    updateTable();
}

function selectForCompare(i) {
    document.getElementById('sel1').value = i;
    updateTable();
    window.scrollTo({ top: document.getElementById('sel1').offsetTop - 100, behavior: 'smooth' });
}

function updateTable() {
    const s = document.getElementById('segSelect').value;
    const c1 = db[s][document.getElementById('sel1').value];
    const c2 = db[s][document.getElementById('sel2').value];
    
    document.getElementById('name1').innerText = c1.name;
    document.getElementById('name2').innerText = c2.name;
    document.getElementById('ratingTarget').innerText = `Seçili Araç: ${c1.name}`;

    const fields = [
        ["Motor Gücü", "motor"], ["Tork Performansı", "tork"], ["Vites Türü", "type"],
        ["Şanzıman Sistemi", "trans"], ["Yakıt Tüketimi", "cons"], ["Boyut & Kapasite", "size"],
        ["Süspansiyon Yapısı", "susp"], ["Güvenlik Donanımı", "safety"]
    ];

    document.getElementById('tableBody').innerHTML = fields.map(f => `
        <tr><td class="label">${f[0]}</td><td>${c1[f[1]]}</td><td>${c2[f[1]]}</td></tr>
    `).join('');
}

// Sosyal Fonksiyonlar
function setRating(e) {
    const rect = e.target.getBoundingClientRect();
    const x = e.clientX - rect.left;
    currentRating = Math.ceil((x / rect.width) * 5);
    document.getElementById('ratingScore').innerText = `Puan: ${currentRating} / 5`;
}

function saveRating() {
    alert("Puanınız başarıyla kaydedildi! Teşekkürler.");
}

function addComment() {
    const name = document.getElementById('userName').value;
    const text = document.getElementById('userComment').value;
    if(!name || !text) return alert("Lütfen boş alan bırakmayın.");
    
    const item = document.createElement('div');
    item.className = 'comment-item';
    item.innerHTML = `<b>${name}:</b> ${text}`;
    document.getElementById('commentList').prepend(item);
    
    document.getElementById('userName').value = "";
    document.getElementById('userComment').value = "";
}

renderApp();
</script>
</body>
</html>
