<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Data Pesanan 5</title>
    <style>
        body {
            font-family: 'Segoe UI', sans-serif;
            margin: 0;
            padding: 0;
            min-height: 100vh;
            background: white;
        }
        .output-container {
            max-width: 1200px;
            overflow: hidden;
            margin : 20px auto 0 auto;
            padding: 0 32px 32px 32px;
            box-sizing: border-box;
            background: 0 8px 32px rgba(0,159,227,0.08);
        }
        .judul-row {
            display: flex;
            flex-direction: row;
            align-items: flex-end;
            justify-content: space-between;
            margin-bottom: 0;
            padding: 0 16px;
        }
        .judul-output {
            font-size: 32px;
            margin: 0;
            color: #009FE3;
            letter-spacing: 0.2px;
            font-weight: 700;
            text-shadow: 0 2px 8px #b3e6fa;
            margin-bottom: 0;
        }
        .tanggal-output {
            display: block;
            text-align: right;
            font-size: 18px;
            color: black;
            font-weight: 500;
            margin-bottom: 0;
            padding-right: 22px;
            margin-left: 24px;
        }
        .main-layout {
            display: flex;
            gap: 24px;
            margin: 24px 0 0 24px;
            max-width: 1200px;
        }
        .left-column, .right-column {
            flex: 3;
        }
        .form-container {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-bottom: 12px;
        }
        .form-item {
            border-collapse: collapse;
            border-spacing: 0;
            background: #fff;
            border-radius: 12px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.06);
            padding: 12px 18px;
        }
        .form-item th {
            font-size: 15px;
            text-align: center;
            padding-bottom: 6px;
        }
        .form-item input,
        .form-item select {
            width: 140px;
            height: 36px;
            font-size: 14px;
            padding: 4px 8px;
            border: 1px solid #009FE3;
            border-radius: 6px;
            box-sizing: border-box;
            background: #f8fafc;
            transition: border 0.2s;
        }
        input:focus, select:focus {
            outline: none;
            border: 1px solid #009FE3;;
            background-color: #e0f4ff;
        }
        th, td {
            border: 1px solid #009FE3;
            padding: 10px 12px;
            text-align: center;
            font-size: 15px;
        }
        #dataTable {
            width: 100%;
            border-collapse: collapse;
            background: linear-gradient(120deg, #fff 0%, #eef4f5 80%);
            box-shadow: 0 6px 24px rgba(0,159,227,0.10);
            overflow: hidden;
            margin-top: 18px;
            border: 2px solid #009fe3
        }
        #dataTable thead th {
            background: linear-gradient(90deg, #fff 0%, #bde3f3 80%);
            color: black;
            font-weight: 700;
            font-size: 16px;
            border-bottom: 2.5px solid #009fe3;
            padding: 14px 16px;
            text-shadow: 0 2px 8px #b3e6fa;
        }
        #dataTable th, #dataTable td {
            border: 1.5px solid #6fd6fb;
            padding: 10px 12px;
            text-align: center;
            background: rgba(255,255,255,0.92);
            transition: background 0.2s, color 0.2s;
        }
        #dataTable tbody tr:hover {
            background: linear-gradient(120deg, #053853 0%, #97cde2 100%);
            box-shadow: 0 2px 8px #2f5e70;
        }
        #dataTable td {
            white-space: normal;
            word-break: break-word;
            vertical-align: top;
        }
        .tr-tidak-normal td {
            background-color: #ecf3f7 !important;
            color: red !important;
            font-weight: 620;
        }
        .screenshot-btn {
            background: linear-gradient(90deg, #009FE3 0%, #00AEFF 100%);;
            border: none;
            border-radius: 50%;
            padding: 8px;
            cursor: pointer;
            box-shadow: 0 2px 8px rgba(99,102,241,0.12);
            transition: transform 0.15s, box-shadow 0.15s;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 84px;
            height: 84px;
            min-width: 84px;
            min-height: 84px;
        }
        .screenshot-btn:hover {
            transform: scale(1.08);
            box-shadow: 0 4px 16px rgba(99,102,241,0.18);
        }
        .screenshot-btn img {
            height: 28px;
            width: 28px;
            display: block;
        }
    </style>
</head>
<body>
    <h3 style="margin-left:16px;">Pengaturan Pesanan Akun</h3>
    <div class="main-layout">
        <div class="left-column">
            <!-- Form input Grup & Pola -->
            <div class="form-container">
                <table class="form-item">
                    <thead>
                        <tr>
                            <th>No. Grup</th>
                            <th>Pola</th>
                            <th>Urutan</th>
                            <th>No. Pesanan</th>
                            <th>No. Nominal</th>
                            <th>No. Status</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td><input type="text" id="nomorGroupInput" placeholder="Nomor Grup"></td>
                            <td>
                                <select id="dropdownPola">
                                    <option value="1">1</option>
                                    <option value="2">2</option>
                                </select>
                            </td>
                            <td><input type="text" id="urutanInput" placeholder="Contoh: 34"></td>
                            <td><input type="text" id="nomorPesananInput" placeholder="Contoh: 000" ></td>
                            <td><input type="text" id="nomorNominalInput" placeholder="Contoh: 11/22" ></td>
                            <td><input type="text" id="nomorStatusInput" placeholder="Contoh: 11/22" ></td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <!-- Grup & Platform -->
            <div class="form-container">
                <table class="form-item">
                    <thead>
                        <tr>
                            <th>Nama Grup</th>
                            <th>Platform</th>
                            <th>Data Pesanan</th>                        
                            <th>Nominal</th>
                            <th>Status</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>
                                <select id="dropdownNamaGroup" >
                                    <option value="ANNIVERSARY">ANNIVERSARY</option>
                                    <option value="REWARDS">REWARDS</option>
                                </select>
                            </td>
                            <td>
                                <select id="dataPlatform">
                                    <option value="LAZADA">LAZADA</option>
                                    <option value="RUPARUPA">RUPARUPA</option>
                                    <option value="BHINNEKA">BHINNEKA</option>
                                    <option value="BLIBLI">BLIBLI</option>
                                    <option value="ZALORA">ZALORA</option>
                                    <option value="TOKOPEDIA">TOKOPEDIA</option>
                                </select>
                            </td>
                            <td><input type="text" id="nomorDataPesananInput" placeholder="Contoh: 13" ></td>
                            <td><input type="text" id="jumlahPesanan1"></td>
                            <td><input type="text" id="statusPesanan1" value="Normal"></td>
                        </tr>
                        <tr>
                            <td>Baris Ke & +No</td>
                            <td><input type="text" id="barisKe" ></td>
                            <td><input type="text" id="tambahNo"></td>
                            <td><input type="text" id="jumlahPesanan2" ></td>
                            <td><input type="text" id="statusPesanan2" value="Tidak Normal" ></td>
                        </tr>
                    </tbody>
                </table>
            
                <div style="display: flex; justify-content: flex-end; margin: 12px 0 24px 0;">
                    <button class="screenshot-btn" id="screenshotTombol" title="Screenshot tabel">
                        <img src="images/lazada.png" alt="Screenshot">
                    </button>
                </div>
            </div>
        </div>

        <div class="right-column"> <!-- Right Column - Nama akun -->
            <div class="form-container">
                <table class="form-item">
                    <thead>
                        <tr>
                            <th colspan="2">Nama Akun</th>
                            <th>Data Pesanan</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>1</td><td><input type="text" id="namaAkun1" placeholder="Kompor 1" value="Hart05"></td>
                            <td><input type="text" id="dataPesanan1" value="Tunggal/Bagian" ></td>
                        </tr>
                        <tr>
                            <td>2</td><td><input type="text" id="namaAkun2" placeholder="Kompor 2" value="Decelina2025"></td>
                            <td><input type="text" id="dataPesanan2" value="Ganda/Bagian"></td>
                        </tr>
                        <tr>
                            <td>3</td><td><input type="text" id="namaAkun3" placeholder="Kompor 3" value="Cutkarlisma" ></td>
                            <td><input type="text" id="dataPesanan3" value="Produk Unggulan" ></td>
                        </tr>
                        <tr>
                            <td>4</td><td><input type="text" id="namaAkun4" placeholder="Tamu" value="" ></td>
                            <td><input type="text" id="dataPesanan4" value="Produk Bekas"></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>

    <div class="output-container">
        <div class="judul-row">
            <h2 class="judul-output">HASIL DATA PENCARIAN PESANAN GRUP</h2>
            <span id="tanggalSekarang" class="tanggal-output"></span>
        </div>
        <table id="dataTable">
            <thead>
                <tr>
                    <th>No.</th>
                    <th>Platform</th>
                    <th>Akun Anggota</th>
                    <th>Nama Grup</th>
                    <th>Nomor Pesanan</th>
                    <th>Data Pesanan</th>
                    <th>Jumlah Pesanan</th>
                    <th>Status Pesanan</th>
                </tr>
            </thead>
            <tbody>
                <tr><td>1 </td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
                <tr><td>2 </td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
                <tr><td>3 </td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
                <tr><td>4 </td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
                <tr><td>5 </td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
                <tr><td>6 </td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
                <tr><td>7 </td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
                <tr><td>8 </td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
                <tr><td>9 </td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
                <tr><td>10</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr>
            </tbody>
        </table>
    </div>

<script src="https://cdn.jsdelivr.net/npm/html2canvas@1.4.1/dist/html2canvas.min.js"></script>
<script>
    // Tampilkan tanggal otomatis
    const now = new Date();
    const tgl = String(now.getDate()).padStart(2, '0');
    const bln = String(now.getMonth() + 1).padStart(2, '0');
    const thn = now.getFullYear();
    document.getElementById("tanggalSekarang").textContent = "Tanggal Pesanan: " +  `${tgl}/${bln}/${thn}`;


    // Update logo screenshot sesuai platform
    function updateScreenshotLogo() {
        const platform = document.getElementById("dataPlatform").value;
        const img = document.querySelector("#screenshotTombol img");
            switch (platform) {
                case "LAZADA"   : img.src= "images/lazada.png"   ; break;
                case "RUPARUPA" : img.src= "images/rupa.png"     ; break;
                case "BHINNEKA" : img.src= "images/bhinneka.png" ; break;
                case "BLIBLI"   : img.src= "images/blibli.png"   ; break;
                case "ZALORA"   : img.src= "images/zalora.png"   ; break;
                case "TOKOPEDIA": img.src= "images/tokopedia.png"; break;
                default         : img.src= "images/lazada.png"   ; break;
            }
    }

    document.getElementById("dataPlatform").addEventListener("change", updateScreenshotLogo);
    document.addEventListener("DOMContentLoaded", updateScreenshotLogo);

    // Screenshot ke clipboard
    document.getElementById("screenshotTombol").addEventListener("click", function() {
        const table = document.getElementById("dataTable");
        if (!table) {
            alert("Tabel tidak ditemukan!");
            return;
        }
        html2canvas(table).then(canvas => {
            canvas.toBlob(blob => {
                if (navigator.clipboard && window.ClipboardItem) {
                    try {
                        const item = new ClipboardItem({ "image/png": blob });
                        navigator.clipboard.write([item]).then(() => {
                            alert("Screenshot tabel berhasil disalin ke clipboard!");
                        }).catch(err => {
                            alert("Gagal menyalin gambar ke clipboard: " + err);
                        });
                    } catch (e) {
                        alert("Clipboard error: " + e);
                    }
                } else {
                    alert("Fitur clipboard tidak didukung di browser ini.");
                }
            }, "image/png");
        }).catch(err => {
            alert("Gagal membuat screenshot: " + err);
        });
    });

    // Daftar semua ID input yang perlu diawasi
    const inputIds = [
        "dataPlatform", "dropdownPola", "urutanInput", "namaAkun1", "namaAkun2", "namaAkun3", "namaAkun4",
        "nomorGroupInput", "nomorPesananInput", "nomorNominalInput", "nomorStatusInput",
        "dropdownNamaGroup", "nomorDataPesananInput", "dataPesanan1", "jumlahPesanan1", "statusPesanan1",
        "dataPesanan2", "jumlahPesanan2", "statusPesanan2", "barisKe", "dataPesanan3", "tambahNo", "dataPesanan4"
    ];

    function prosesOutput() {
        const table = document.getElementById('dataTable');
        const baris = document.querySelectorAll("#dataTable tbody tr");
        const platform = document.getElementById("dataPlatform").value;
        const pola = document.getElementById("dropdownPola").value;
        const urutan = document.getElementById("urutanInput").value;
        const nomorDataPesanan = document.getElementById("nomorDataPesananInput").value;
        const nomorNominalInput = document.getElementById("nomorNominalInput").value;
        const nomorStatusInput = document.getElementById("nomorStatusInput").value;
        const namaGrup = document.getElementById("dropdownNamaGroup").value;
        const nomorGrup = document.getElementById("nomorGroupInput").value;
        const nomorPesanan = document.getElementById("nomorPesananInput").value;
        const barisKe = parseInt(document.getElementById("barisKe").value, 10);
        const tambahNo = parseInt(document.getElementById("tambahNo").value, 10);


        const namaAkun = [
            document.getElementById("namaAkun1").value,
            document.getElementById("namaAkun2").value,
            document.getElementById("namaAkun3").value,
            document.getElementById("namaAkun4").value
        ];
        const dataPesanan = [
            document.getElementById("dataPesanan1").value,
            document.getElementById("dataPesanan2").value,
            document.getElementById("dataPesanan3").value,
            document.getElementById("dataPesanan4").value
        ];
        const jumlahPesanan = [
            document.getElementById("jumlahPesanan1").value,
            document.getElementById("jumlahPesanan2").value
        ];
        const statusPesanan = [
            document.getElementById("statusPesanan1").value,
            document.getElementById("statusPesanan2").value
        ];

        // ambil tanggal hari ini
        const today = new Date();
        const yyyy = today.getFullYear();
        const mm = String(today.getMonth() +1).padStart(2, '0');
        const dd = String(today.getDate()).padStart(2, '0');
        const kombinasiNamaGrup = `${namaGrup}-${mm}${dd}${nomorGrup}`;
        const tanggalHariIni = `${dd}/${mm}/${yyyy}`;


        //TENTUKAN URUTAN AKUN BERDASARKAN POLA
        let urutanAkun = [];
        if (pola === "1") {
            urutanAkun = [1, 2, 3, 4];
        } else if (pola === "2") {
            urutanAkun = [1, 1, 2, 2, 3, 3, 4, 4];
        }
        //MASUKKAN POLA KHUSUS INPUT, UBAH URUTAN POSISI AKUN 4
        if (urutan) {
            const angka = urutan.split("").map(n => parseInt(n, 10)); //ubah urutan input jadi angka
            if(pola === "1") {
                urutanAkun = [1,2,3]; 
            } else if (pola === "2") {
                urutanAkun = [1,1,2,2,3,3]; 
            }
            //GANTI POSISI SESUAI ANGKA URUTAN
            angka.forEach((pos, idx) => {
                //index dalam array dimulai dari 0, pos dari user mulai dari 1
                const insertIndex = pos - 1;
                if (insertIndex <= urutanAkun.length) {
                    urutanAkun.splice(insertIndex, 0, 4);   
                }
            });
            urutanAkun = urutanAkun.slice(0, 10); //batas 10 baris
        }

        //PROSES SETIAP BARIS TABEL
        for (let i = 0; i < baris.length; i++) {
            const row = baris[i];
            const cell = row.querySelectorAll("td");

            if (i < urutanAkun.length) {
                console.log(`Memproses baris ke-${i + 1}`);
                //MASUKKAN NAMA AKUN BERDASARKAN URUTAN
                const akunIndex = urutanAkun[i] - 1; // indeks akun
                cell[2].textContent = namaAkun[akunIndex] || ""; // isi kolom akun anggota
                cell[3].textContent = kombinasiNamaGrup; // isi kolom nama grup

                //TAMBAHKAN LOGIKA UNTUK MENAMPILKAN DATA PESANAN
                if (akunIndex === 3) { // jika akun 4
                    //ambil nomor data pesanan input dan ubah menjadi array angka
                    const nomorPesananArray = nomorDataPesanan.split("").map(n => parseInt(n, 10)).filter(n => !isNaN(n)); // filter NaN

                    //tentukan data pesanan berdasarkan nomor data pesanan
                    if (nomorPesananArray.length > 0) {
                        //gunakan indeks baris untuk menentukan angka mana yang digunakan
                        const dataIndex = nomorPesananArray[i % nomorPesananArray.length] - 1; // indeks data pesanan
                        if (dataIndex >= 0 && dataIndex < dataPesanan.length) {
                            cell[5].textContent = dataPesanan[dataIndex] || ""; // isi kolom data pesanan 
                        } else {
                            cell[5].textContent = ""; // jkosongkan jika indeks tidak valid
                        }
                    } else {
                        cell[5].textContent = ""; //kosongkan jika tidak ada input
                    }
                } else {
                    if (pola === "1") {
                        cell[5].textContent = dataPesanan[2]; //produk unggulan
                    } else if (pola === "2") {
                        //bergantian antara tunggal/bagian dan produk unggulan
                        cell[5].textContent = i % 2 === 0 ? dataPesanan[0] : dataPesanan[2]; //isi kolom data pesanan
                    }
                }

                if (akunIndex === 3) { // jika akun 4
                    const nomorNominalArray = nomorNominalInput.split("").map(n => parseInt(n, 10)).filter(n => !isNaN(n)); //filter NaN
                    if(nomorNominalArray.length > 0) {
                        const nominalIndex = nomorNominalArray[i % nomorNominalArray.length] - 1; //indeks nominal berdasarkan input
                        if (nominalIndex >= 0 && nominalIndex < jumlahPesanan.length) {
                            cell[6].textContent = jumlahPesanan[nominalIndex] || ""; //isi nominal sesuai input
                        } else {
                            cell[6].textContent = ""; //kosongkan jika indeks tidak valid
                        }
                    } else {
                        cell[6].textContent = ""; //kosongkan jika tidak ada input
                    }
                } else {
                    cell[6].textContent = jumlahPesanan[0] || ""; // default untuk nama akun 1,2,3
                }

                if (akunIndex === 3) { // jika akun 4
                    const nomorStatusArray = nomorStatusInput.split("").map(n => parseInt(n, 10)).filter(n => !isNaN(n)); //filter NaN
                    if(nomorStatusArray.length > 0) {
                        const statusIndex = nomorStatusArray[i % nomorStatusArray.length] - 1; //indeks nominal berdasarkan input
                        if (statusIndex >= 0 && statusIndex < statusPesanan.length) {
                            cell[7].textContent = statusPesanan[statusIndex] || ""; //isi nominal sesuai input
                                if(cell[7] && cell[7].textContent.trim().toLowerCase() === "tidak normal") {
                                    row.classList.add("tr-tidak-normal");
                                } else {
                                    row.classList.remove("tr-tidak-normal");
                                }
                        } else {
                            cell[7].textContent = ""; //kosongkan jika indeks tidak valid
                        }
                    } else {
                        cell[7].textContent = ""; //kosongkan jika tidak ada input
                    }
                } else {
                    cell[7].textContent = statusPesanan[0] || ""; // default untuk nama akun 1,2,3
                }

                // hitung nomor pesanan berdasarkan baris ke dan tambah no
                const barisKeArray = String(barisKe)
                    .split('') //ubah ke array contoh ['1', '2', '3']
                    .map(Num => parseInt(Num, 10)); //jadikan angka [1,2,3]
                let nomorPesananBaris = parseInt(nomorPesanan || '0', 10); //nomor pesanan default dengan mengisi || '0' untuk memastikan bukan NaN
                // jika barisKe terisi, maka tambahkan nilai tambahNo
                if (barisKeArray.includes(i + 1) && !isNaN(tambahNo)) { 
                    nomorPesananBaris += tambahNo;
                }
                const kombinasiNomorPesanan = `${yyyy}${mm}${dd}${String(nomorPesananBaris).padStart(3, '0')}`; // format nomor pesanan
                cell[4].textContent = kombinasiNomorPesanan; // isi kolom nomor pesanan

                //buat logo dan teks platform
                const wrapper = document.createElement("div");
                      wrapper.style.display = "flex";
                      wrapper.style.alignItems = "center";
                      wrapper.style.justifyContent = "center";
                      wrapper.style.gap = "5px"; // jarak antara logo dan nama platform
                //buat logo platform   
                const logo = document.createElement("img");
                      logo.style.height = '26px'; // tinggi logo
                      logo.alt = platform; // set alt text

                    switch (platform) {
                        case "LAZADA"   : logo.src= "images/lazada.png"   ; break;
                        case "RUPARUPA" : logo.src= "images/rupa.png"     ; break;
                        case "BHINNEKA" : logo.src= "images/bhinneka.png" ; break;
                        case "BLIBLI"   : logo.src= "images/blibli.png"   ; break;
                        case "ZALORA"   : logo.src= "images/zalora.png"   ; break;
                        case "TOKOPEDIA": logo.src= "images/tokopedia.png"; break;
                        default         : logo.src= ""                    ; break; // logo default
                    }

                //tambahkan nama platform
                const platformText = document.createElement("span");
                      platformText.style.fontSize = '14px';
                      platformText.style.lineHeight = '26px';
                      platformText.textContent = platform;
                //masukkan ke wrapper
                      wrapper.appendChild(logo);
                      wrapper.appendChild(platformText);
                //masukkan wrapper ke kolom platform
                cell[1].textContent = ""; // hapus teks sebelumnya
                cell[1].appendChild(wrapper);
            } else {
                    // Kosongkan baris-baris selebihnya
                    for (let j = 1; j < cell.length; j++) {
                    cell[j].innerText = '';
                    }
            }
        }
        for (let i = 0; i < baris.length; i++) {
            const row = baris[i];
            const cell = row.querySelectorAll("td");
            // ...semua proses pengisian cell...
            // --- Tambahkan logika ini di akhir loop ---
            if (cell[7] && cell[7].textContent.trim().toLowerCase() === "tidak normal") {
                row.classList.add("tr-tidak-normal");
            } else {
                row.classList.remove("tr-tidak-normal");
            }
        }
        simpanData(); //simpan data ke localstrorage
    }

    // Fungsi simpan dan ambil data tetap seperti sebelumnya
    function simpanData() {
        const data = {};
        inputIds.forEach(id => {
            const el = document.getElementById(id);
            if (el) data[id] = el.value;
        });
        // simpan hasil output tabel
        const baris = document.querySelectorAll("#dataTable tbody tr");
        const hasilOutput = [];
        for (let i = 0; i < baris.length; i++) {
            const cell = baris[i].querySelectorAll("td");
            const rowData = [];
            for (let j = 0; j < cell.length; j++) {
                rowData.push(cell[j].innerHTML);
            }
            hasilOutput.push(rowData);
        }
        data.hasilOutput = hasilOutput;
        localStorage.setItem("formData", JSON.stringify(data));
    }

    function ambilData() {
        const data = JSON.parse(localStorage.getItem("formData"));
        if (data) {
            inputIds.forEach(id => {
                const el = document.getElementById(id);
                if (el && data[id] !== undefined) el.value = data[id];
            });
            // isi tabel output
            if (data.hasilOutput) {
                const baris = document.querySelectorAll("#dataTable tbody tr");
                for (let i = 0; i < baris.length; i++) {
                    const row = baris[i];
                    const cell =row.querySelectorAll("td");
                    if (data.hasilOutput[i]) {
                        for (let j = 0; j < cell.length; j++) {
                            cell[j].innerHTML = data.hasilOutput[i][j];
                        }
                        row.classList.remove("tr-tidak-normal");
                    }
                }
            }
        }
        prosesOutput();
    }

                 
    

    // Otomatis ambil data saat halaman dimuat
    document.addEventListener("DOMContentLoaded", () => {
        ambilData();
    });
    document.addEventListener("DOMContentLoaded", updateScreenshotLogo);
    document.getElementById("dataPlatform").addEventListener("change", updateScreenshotLogo);

    // Event listener untuk input
    inputIds.forEach(id => {
        const el = document.getElementById(id);
        if (el) {
            el.addEventListener("input", prosesOutput);
            el.addEventListener("change", prosesOutput);
        }
    });

    document.getElementById("screenshotTombol").addEventListener("click", function() {
        const table = document.getElementById("dataTable");
        if (!table) {
            alert("Tabel tidak ditemukan");
            return;
        }
        html2canvas(table).then(canvas => {
            canvas.toBlob(blob => {
                if (navigator.clipboard && window.ClipboardItem) {
                    try {
                        const item = new ClipboardItem({ "image/png": blob });
                        navigator.clipboard.write([item]).then(() => {
                            alert("Screenshot tabel berhasil disalin ke clipboard!");
                        }).catch(err => {
                            alert("Gagal menyalin gambar ke clipboard: " + err);
                        });
                    } catch (e) {
                        alert("Clipboard error: " + e);
                    }
                } else {
                    alert("Fitur clipboard tidak didukung di browser ini.");
                }
            }, "image/png");
        }).catch(err => {
            alert("Gagal membuat screenshot: " + err);
        });
    })

</script>
</body>
</html>
