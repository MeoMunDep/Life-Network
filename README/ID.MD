### 🚀 Panduan Instalasi Bot life-network

Selamat datang di panduan instalasi bot! Ikuti langkah-langkah di bawah ini untuk menginstal dan mengonfigurasi bot dengan benar. Panduan ini dibuat untuk pengguna baru dengan penjelasan yang mudah dipahami.

📱 **Untuk pengguna ponsel (Termux):** [Lihat panduan di sini](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## Daftar Isi

1. [Persyaratan Sistem](#persyaratan-sistem)
2. [Instalasi Bot](#instalasi-bot)
3. [Konfigurasi Bot](#konfigurasi-bot)
4. [Menjalankan Bot](#menjalankan-bot)
5. [Memperbarui Bot](#memperbarui-bot)
6. [Kontak & Dukungan](#kontak--dukungan)

---

## Persyaratan Sistem

Sebelum menjalankan bot, pastikan kamu telah menginstal:

* **Node.js** (Versi: `22.11.0`)
* **npm** (Versi: `10.9.0`)
* **Git**
* **Docker** *(Opsional)*

📥 **Node.js & npm:** [Unduh di sini](https://t.me/KeoAirDropFreeNe/257/1462)
📥 **Git:** [Unduh di sini](https://t.me/KeoAirDropFreeNe/257/60831)

---

## Instalasi Bot

<details>
<summary><strong>🔧 Instal melalui Git</strong></summary>

```bash
git clone https://github.com/MeoMunDep/life-network.git
cd life-network
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger bs58 @solana/web3.js tweetnacl
```

</details>

<details>
<summary><strong>🧰 Instal Manual</strong></summary>

1. Unduh dan ekstrak file bot secara manual.
2. Jalankan perintah `npm install` seperti di atas.

</details>

<details>
<summary><strong>🐳 Instal melalui Docker</strong></summary>

```bash
docker build -t life-network-image .
docker run -d --name life-network-container -v $(pwd)/logs:/app/logs life-network-image
```

> 💡 Di **Windows CMD**, gunakan `%cd%` alih-alih `$(pwd)`

</details>

---

## Konfigurasi Bot

<details open>
<summary><strong>📜 1. <code>configs.json</code> - Konfigurasi Utama</strong></summary>

```json
{
  "proxyMode": "round",
  "rotateProxy": false,
  "skipInvalidProxy": true,
  "proxyRotationInterval": 2,
  "delayEachAccount": [1, 1],
  "timeToRestartAllAccounts": 300,
  "howManyAccountsRunInOneTime": 1,
  "doTasks": true,
  "connectWallets": true,
  "bindReferralCodes": true,
  "referralCodes": ["SC315", "NZVI4"]
}
```

| **Nama Parameter**            | **Tipe**          | **Default** | **Deskripsi**                            |
| ----------------------------- | ----------------- | ----------- | ---------------------------------------- |
| `rotateProxy`                 | `boolean`         | `false`     | Aktifkan rotasi proxy antar akun         |
| `proxyMode`                   | `string`          | `static`    | Mode penggunaan proxy                    |
| `skipInvalidProxy`            | `boolean`         | `false`     | Lewati akun dengan proxy tidak valid     |
| `proxyRotationInterval`       | `number`          | `2`         | Interval rotasi proxy (menit)            |
| `delayEachAccount`            | `[number,number]` | `[5,8]`     | Jeda acak antar akun (detik)             |
| `timeToRestartAllAccounts`    | `number`          | `300`       | Waktu sebelum restart semua akun (detik) |
| `howManyAccountsRunInOneTime` | `number`          | `100`       | Jumlah akun yang berjalan bersamaan      |
| `doTasks`                     | `boolean`         | `true`      | Menjalankan tugas utama atau tidak       |
| `connectWallets`              | `boolean`         | `true`      | Hubungkan dompet Solana                  |
| `bindReferralCodes`           | `boolean`         | `true`      | Gunakan kode referral                    |
| `referralCodes`               | `string[]`        | `[""]`      | Daftar kode referral (opsional)          |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> - Data Pengguna</strong></summary>

📥 [Panduan dari Telegram](https://t.me/KeoAirDropFreeNee/1586)

```txt
ey...
ey...
ey...
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> - Daftar Proxy</strong></summary>

📥 [Proxy gratis dari Webshare](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
...
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> - Daftar Dompet</strong></summary>

📥 [Buat dompet di sini](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
solana privatekey
solana privatekey
solana privatekey
...
```

</details>

---

## Menjalankan Bot

<details open>
<summary><strong>🪟 Jalankan di Windows (.bat)</strong></summary>

1. Klik dua kali `run.bat`
2. Script akan memperbarui, menginstal dependensi, dan menjalankan bot secara otomatis.

> Jika gagal, klik kanan → **Run as Administrator**
> Atau jalankan lewat CMD:

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 Jalankan di Linux/macOS (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 Jalankan dengan Docker</strong></summary>

```bash
docker stop life-network-container 2>/dev/null && docker rm life-network-container 2>/dev/null
docker build -t life-network-image .
docker run -d --name life-network-container -v $(pwd)/logs:/app/logs life-network-image
```

> Untuk memulai ulang nanti:

```bash
docker start life-network-container
```

</details>

---

## Memperbarui Bot

<details>
<summary><strong>🔄 Jika diinstal melalui Git</strong></summary>

```bash
cd life-network
git pull origin main
npm install
```

</details>

<details>
<summary><strong>🐳 Jika menggunakan Docker</strong></summary>

```bash
docker stop life-network-container
docker rm life-network-container
docker build -t life-network-image .
docker run -d --name life-network-container life-network-image
```

</details>

---

## Kontak & Dukungan

* **Dukung saya melalui** [Tautan Referral](https://airdrop.lifenetworks.io?ref=ZIIPN)
* **Donasi:** [Donasi di sini](https://t.me/KeoAirDropFreeNe/312/27801)
* **Kontak (Kerja):** [@MeoMunDep](https://t.me/MeoMunDep)
* **Grup Dukungan:** [Gabung di sini](https://t.me/KeoAirDropFreeNe)
* **Kanal Pembaruan:** [Lihat kanal](https://t.me/KeoAirDropFreeNee)
* **YouTube:** [Tonton di sini](https://www.youtube.com/@keoairdropfreene)
* **Instagram:** [Ikuti](https://www.instagram.com/meomundep)
* **Tiktok:** [Ikuti](https://www.tiktok.com/@meomundep)

---

⚠️ **Penafian:** Kode ini disediakan “sebagaimana adanya” tanpa jaminan apa pun. Gunakan dengan risiko Anda sendiri. Dilarang keras menjual atau mendistribusikan ulang kode ini dalam bentuk apa pun.

✨ Terima kasih telah menggunakan bot ini — semoga Anda sukses dan mendapat banyak hasil dari skrip ini! 🚀
