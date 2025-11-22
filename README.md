<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Jam Digital</title>

<style>
    body {
        margin: 0;
        background: black;
        color: #00e5ff;
        font-family: Arial, Helvetica, sans-serif;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100vh;
        text-align: center;
    }

    #clock {
        font-size: 23vw;
        font-weight: bold;
        letter-spacing: 0.03em;
        line-height: 1;
        margin-bottom: 2vh;
    }

    #date {
        font-size: 6vw;
        font-weight: normal;
        letter-spacing: 0.05em;
    }
</style>

<script>
function updateClock() {
    let now = new Date();

    // --- Jam ---
    let h = String(now.getHours()).padStart(2, '0');
    let m = String(now.getMinutes()).padStart(2, '0');
    let s = String(now.getSeconds()).padStart(2, '0');
    document.getElementById("clock").textContent = h + ":" + m + ":" + s;

    // --- Hari & Tanggal Indonesia ---
    let hari = ["Minggu", "Senin", "Selasa", "Rabu", "Kamis", "Jumat", "Sabtu"];
    let bulan = [
        "Januari", "Februari", "Maret", "April", "Mei", "Juni",
        "Juli", "Agustus", "September", "Oktober", "November", "Desember"
    ];

    let namaHari = hari[now.getDay()];
    let tanggal = now.getDate();
    let namaBulan = bulan[now.getMonth()];
    let tahun = now.getFullYear();

    document.getElementById("date").textContent =
        namaHari + ", " + tanggal + " " + namaBulan + " " + tahun;
}

setInterval(updateClock, 500);
</script>

</head>
<body onload="updateClock()">

    <div id="clock">00:00:00</div>
    <div id="date">Senin, 1 Januari 2025</div>

</body>
</html>
