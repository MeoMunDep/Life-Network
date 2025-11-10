### 🚀 Hướng Dẫn Cài Đặt Bot life-network

Chào mừng bạn đến với hướng dẫn cài đặt bot! Hãy làm theo các bước bên dưới để cài đặt và cấu hình bot đúng cách. Tài liệu này được viết dành cho người mới, với mô tả dễ hiểu cho từng bước.

📱 **Dành cho người dùng Mobile (Termux):** [Xem hướng dẫn tại đây](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## Mục Lục

1. [Yêu Cầu Hệ Thống](#yêu-cầu-hệ-thống)
2. [Cài Đặt Bot](#cài-đặt-bot)
3. [Cấu Hình Bot](#cấu-hình-bot)
4. [Chạy Bot](#chạy-bot)
5. [Cập Nhật Bot](#cập-nhật-bot)
6. [Liên Hệ & Hỗ Trợ](#liên-hệ--hỗ-trợ)

---

## Yêu Cầu Hệ Thống

Trước khi chạy bot, hãy đảm bảo bạn đã cài đặt:

* **Node.js** (Phiên bản: `22.11.0`)
* **npm** (Phiên bản: `10.9.0`)
* **Git**
* **Docker** *(Không bắt buộc)*

📥 **Node.js & npm:** [Tải tại đây](https://t.me/KeoAirDropFreeNe/257/1462)

📥 **Git:** [Tải tại đây](https://t.me/KeoAirDropFreeNe/257/60831)

---

## Cài Đặt Bot

<details>
<summary><strong>🔧 Cài Đặt qua Git</strong></summary>

```bash
git clone https://github.com/MeoMunDep/life-network.git
cd life-network
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger bs58 @solana/web3.js tweetnacl
```

</details>

<details>
<summary><strong>🧰 Cài Đặt Thủ Công</strong></summary>

1. Tải xuống và giải nén bot.
2. Chạy lệnh `npm install` giống như trên.

</details>

<details>
<summary><strong>🐳 Cài Đặt bằng Docker</strong></summary>

```bash
docker build -t life-network-image .
docker run -d --name life-network-container -v $(pwd)/logs:/app/logs life-network-image
```

> 💡 Trên **Windows CMD**, dùng `%cd%` thay vì `$(pwd)`

</details>

---

## Cấu Hình Bot

<details open>
<summary><strong>📜 1. <code>configs.json</code> - Cấu Hình Chính</strong></summary>

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

| **Tên Tham Số**               | **Loại**           | **Mặc Định** | **Mô Tả**                                   |
| ----------------------------- | ------------------ | ------------ | ------------------------------------------- |
| `rotateProxy`                 | `boolean`          | `false`      | Bật xoay proxy giữa các tài khoản           |
| `proxyMode`                   | `string`           | `static`     | Chế độ sử dụng proxy                        |
| `skipInvalidProxy`            | `boolean`          | `false`      | Bỏ qua tài khoản nếu proxy lỗi              |
| `proxyRotationInterval`       | `number`           | `2`          | Thời gian (phút) giữa mỗi lần xoay proxy    |
| `delayEachAccount`            | `[number, number]` | `[5, 8]`     | Delay ngẫu nhiên (giây) giữa các tài khoản  |
| `timeToRestartAllAccounts`    | `number`           | `300`        | Thời gian (giây) reset lại tất cả tài khoản |
| `howManyAccountsRunInOneTime` | `number`           | `100`        | Số tài khoản chạy song song cùng lúc        |
| `doTasks`                     | `boolean`          | `true`       | Có làm nhiệm vụ hay không                   |
| `connectWallets`              | `boolean`          | `true`       | Có kết nối ví Solana hay không              |
| `bindReferralCodes`           | `boolean`          | `true`       | Có nhập mã giới thiệu hay không             |
| `referralCodes`               | `string[]`         | `[""]`       | Mã giới thiệu tùy chọn                      |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> - Danh Sách User Data</strong></summary>

📥 [Hướng dẫn từ Telegram](https://t.me/KeoAirDropFreeNee/1586)

```txt
ey...
ey...
ey...
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> - Danh Sách Proxy</strong></summary>

📥 [Proxy miễn phí từ Webshare](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
...
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> - Danh Sách Ví</strong></summary>

📥 [Tạo ví tại đây](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
solana privatekey
solana privatekey
solana privatekey
...
```

</details>

---

## Chạy Bot

<details open>
<summary><strong>🪟 Chạy trên Windows (.bat)</strong></summary>

1. Nhấn đúp `run.bat`
2. File sẽ tự động cập nhật, cài dependencies và chạy bot.

> Nếu lỗi, nhấn chuột phải → **Run as Administrator**
> Hoặc chạy bằng CMD:

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 Chạy trên Linux/macOS (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 Chạy bằng Docker</strong></summary>

```bash
docker stop life-network-container 2>/dev/null && docker rm life-network-container 2>/dev/null
docker build -t life-network-image .
docker run -d --name life-network-container -v $(pwd)/logs:/app/logs life-network-image
```

> Khởi động lại sau này:

```bash
docker start life-network-container
```

</details>

---

## Cập Nhật Bot

<details>
<summary><strong>🔄 Nếu cài qua Git</strong></summary>

```bash
cd life-network
git pull origin main
npm install
```

</details>

<details>
<summary><strong>🐳 Nếu dùng Docker</strong></summary>

```bash
docker stop life-network-container
docker rm life-network-container
docker build -t life-network-image .
docker run -d --name life-network-container life-network-image
```

</details>

---

## Liên Hệ & Hỗ Trợ

* **Ủng hộ mình qua** [Link Referral](https://airdrop.lifenetworks.io?ref=ZIIPN)
* **Donate:** [Donate tại đây](https://t.me/KeoAirDropFreeNe/312/27801)
* **Liên hệ (Công việc):** [@MeoMunDep](https://t.me/MeoMunDep)
* **Nhóm hỗ trợ:** [Tham gia tại đây](https://t.me/KeoAirDropFreeNe)
* **Kênh cập nhật:** [Xem kênh](https://t.me/KeoAirDropFreeNee)
* **YouTube:** [Xem tại đây](https://www.youtube.com/@keoairdropfreene)
* **Instagram:** [Theo dõi](https://www.instagram.com/meomundep)
* **Tiktok:** [Theo dõi](https://www.tiktok.com/@meomundep)

---

⚠️ **Lưu ý**: Mã nguồn được cung cấp “như hiện trạng” và không có bất kỳ cam kết hay bảo đảm nào. Bạn tự chịu trách nhiệm với mọi rủi ro phát sinh. Nghiêm cấm bán lại hoặc phân phối mã nguồn này dưới bất kỳ hình thức nào.

✨ Cảm ơn bạn đã sử dụng bot, chúc bạn kiếm được nhiều từ script của mình! Chúc may mắn! 🚀
