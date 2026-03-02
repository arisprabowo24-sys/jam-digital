<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jadwal Shalat Masjid Darussalam</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            height: 100vh;
            background-image: linear-gradient(rgba(0,0,0,0.3), rgba(0,0,0,0.3)), url('JAM MASJID/bg-masjid.jpg');
            background-size: cover;
            background-position: center;
            color: white;
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }

        /* HEADER */
        header {
            background: rgba(0, 0, 0, 0.7);
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 4px solid #ffd700;
        }

        .masjid-info h1 {
            font-size: 2.5rem;
            color: #ffd700;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        .clock-container {
            text-align: right;
        }

        #jam {
            font-size: 3.5rem;
            font-weight: bold;
            display: block;
        }

        #tanggal {
            font-size: 1.2rem;
        }

        /* MAIN AREA */
        .container {
            flex: 1;
            display: flex;
            padding: 20px;
            gap: 20px;
        }

        .sidebar {
            width: 350px;
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .card {
            background: rgba(0, 0, 0, 0.6);
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .card-header {
            background: #2e7d32;
            padding: 10px;
            text-align: center;
            font-weight: bold;
            font-size: 1.1rem;
        }

        .card-body {
            padding: 15px;
        }

        .row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-size: 1rem;
        }

        .total {
            border-top: 1px solid #ffd700;
            padding-top: 5px;
            color: #ffd700;
            font-weight: bold;
        }

        /* JADWAL SHALAT (BAWAH) */
        .footer-jadwal {
            background: rgba(0, 0, 0, 0.8);
            display: grid;
            grid-template-columns: repeat(6, 1fr);
            padding: 10px 0;
            border-top: 4px solid #2e7d32;
        }

        .sholat-item {
            text-align: center;
            border-right: 1px solid rgba(255,255,255,0.1);
        }

        .sholat-item:last-child { border: none; }

        .sholat-name {
            font-size: 1.2rem;
            color: #ffd700;
            display: block;
        }

        .sholat-time {
            font-size: 2rem;
            font-weight: bold;
        }

        /* RUNNING TEXT */
        .running-text {
            background: #2e7d32;
            color: white;
            padding: 10px 0;
            font-size: 1.2rem;
        }

        marquee {
            width: 100%;
        }
    </style>
</head>
<body>

    <header>
        <div class="masjid-info">
            <h1>MASJID DARUSSALAM</h1>
            <p>PERUM JATISAWIT ASRI,JITENGAN,BALECATUR,GAMPING,SLEMAN</p>
        </div>
        <div class="clock-container">
            <span id="jam">00:00:00</span>
            <span id="tanggal">Senin, 01 Januari 2024</span>
        </div>
    </header>

    <div class="container">
        <aside class="sidebar">
            <div class="card">
                <div class="card-header">SALDO KAS MASJID</div>
                <div class="card-body">
                    <div class="row"><span>SALDO AWAL</span><span>15.000.000</span></div>
                    <div class="row"><span>PEMASUKAN</span><span>1.000.000</span></div>
                    <div class="row"><span>PENGELUARAN</span><span>500.000</span></div>
                    <div class="row total"><span>SALDO AKHIR</span><span>15.500.000</span></div>
                </div>
            </div>

            <div class="card">
                <div class="card-header">PETUGAS JUM'AT</div>
                <div class="card-body">
                    <div class="row"><span>IMAM</span><span>UST.LUKMAN JOHAN</span></div>
                    <div class="row"><span>KHATIB</span><span>UST.LUKMAN JOHAN</span></div>
                    <div class="row"><span>MUADZIN</span><span>UST JATMIKO</span></div>
                </div>
            </div>
        </aside>

        </div>

    <div class="footer-jadwal">
        <div class="sholat-item">
            <span class="sholat-name">SUBUH</span>
            <span class="sholat-time">04:35</span>
        </div>
        <div class="sholat-item">
            <span class="sholat-name">DZUHUR</span>
            <span class="sholat-time">12:05</span>
        </div>
        <div class="sholat-item">
            <span class="sholat-name">ASHAR</span>
            <span class="sholat-time">15:15</span>
        </div>
        <div class="sholat-item">
            <span class="sholat-name">MAGHRIB</span>
            <span class="sholat-time">18:10</span>
        </div>
        <div class="sholat-item">
            <span class="sholat-name">ISYA</span>
            <span class="sholat-time">19:20</span>
        </div>
        <div class="sholat-item">
            <span class="sholat-name">SYURUQ</span>
            <span class="sholat-time">05:55</span>
        </div>
    </div>

    <div class="running-text">
        <marquee behavior="scroll" direction="left">
            "Barangsiapa yang membangun masjid karena Allah, maka Allah akan membangunkan baginya rumah di surga." (HR. Bukhari & Muslim) — Jagalah kebersihan Masjid kita — Matikan Handphone saat berada di dalam Masjid — Luruskan Shaf sebelum Shalat dimulai.
        </marquee>
    </div>

    <script>
        function updateClock() {
            const now = new Date();
            
            // Jam
            const h = String(now.getHours()).padStart(2, '0');
            const m = String(now.getMinutes()).padStart(2, '0');
            const s = String(now.getSeconds()).padStart(2, '0');
            document.getElementById('jam').innerText = `${h}:${m}:${s}`;

            // Tanggal
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            document.getElementById('tanggal').innerText = now.toLocaleDateString('id-ID', options);
        }

        setInterval(updateClock, 1000);
        updateClock();
    </script>
</body>
</html>
