### 🚀 life-network 봇 설치 가이드

봇 설치 가이드에 오신 것을 환영합니다! 아래 단계를 따라 하면 봇을 올바르게 설치하고 설정할 수 있습니다. 이 문서는 초보자도 이해하기 쉽게 작성되었습니다.

📱 **모바일 사용자(Termux):** [여기에서 가이드 보기](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## 목차

1. [시스템 요구사항](#시스템-요구사항)
2. [봇 설치](#봇-설치)
3. [봇 설정](#봇-설정)
4. [봇 실행](#봇-실행)
5. [봇 업데이트](#봇-업데이트)
6. [문의 & 지원](#문의--지원)

---

## 시스템 요구사항

봇을 실행하기 전에 아래 프로그램이 설치되어 있어야 합니다:

* **Node.js** (버전: `22.11.0`)
* **npm** (버전: `10.9.0`)
* **Git**
* **Docker** *(선택사항)*

📥 **Node.js & npm:** [다운로드](https://t.me/KeoAirDropFreeNe/257/1462)

📥 **Git:** [다운로드](https://t.me/KeoAirDropFreeNe/257/60831)

---

## 봇 설치

<details>
<summary><strong>🔧 Git으로 설치</strong></summary>

```bash
git clone https://github.com/MeoMunDep/life-network.git
cd life-network
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger bs58 @solana/web3.js tweetnacl
```

</details>

<details>
<summary><strong>🧰 수동 설치</strong></summary>

1. 봇 파일을 수동으로 다운로드 및 압축 해제합니다.
2. 위와 동일한 `npm install` 명령어를 실행합니다.

</details>

<details>
<summary><strong>🐳 Docker로 설치</strong></summary>

```bash
docker build -t life-network-image .
docker run -d --name life-network-container -v $(pwd)/logs:/app/logs life-network-image
```

> 💡 **Windows CMD**에서는 `$(pwd)` 대신 `%cd%` 사용

</details>

---

## 봇 설정

<details open>
<summary><strong>📜 1. <code>configs.json</code> - 기본 설정</strong></summary>

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

| **설정 이름**                     | **타입**             | **기본값**  | **설명**                    |
| ----------------------------- | ------------------ | -------- | ------------------------- |
| `rotateProxy`                 | `boolean`          | `false`  | 계정마다 프록시 순환 사용 여부         |
| `proxyMode`                   | `string`           | `static` | 프록시 작동 모드                 |
| `skipInvalidProxy`            | `boolean`          | `false`  | 잘못된 프록시가 있을 경우 해당 계정 건너뛰기 |
| `proxyRotationInterval`       | `number`           | `2`      | 프록시 변경 간격(분)              |
| `delayEachAccount`            | `[number, number]` | `[5, 8]` | 계정 실행 간 랜덤 지연(초)          |
| `timeToRestartAllAccounts`    | `number`           | `300`    | 모든 계정을 다시 시작하기 전 대기 시간(초) |
| `howManyAccountsRunInOneTime` | `number`           | `100`    | 동시에 실행할 계정 수              |
| `doTasks`                     | `boolean`          | `true`   | 작업 수행 여부                  |
| `connectWallets`              | `boolean`          | `true`   | Solana 지갑 연결 여부           |
| `bindReferralCodes`           | `boolean`          | `true`   | 추천 코드 자동 입력 여부            |
| `referralCodes`               | `string[]`         | `[""]`   | 선택적 추천 코드                 |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> - 사용자 데이터 목록</strong></summary>

📥 [텔레그램 가이드](https://t.me/KeoAirDropFreeNee/1586)

```txt
ey...
ey...
ey...
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> - 프록시 목록</strong></summary>

📥 [무료 Webshare 프록시](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
...
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> - 지갑 목록</strong></summary>

📥 [지갑 생성 도구](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
solana privatekey
solana privatekey
solana privatekey
...
```

</details>

---

## 봇 실행

<details open>
<summary><strong>🪟 Windows에서 실행 (.bat)</strong></summary>

1. `run.bat` 더블 클릭
2. 자동 업데이트, 의존성 설치 후 봇 실행

> 실행 실패 시: 우클릭 → **관리자 권한으로 실행**
> 또는 CMD에서 실행:

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 Linux/macOS에서 실행 (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 Docker로 실행</strong></summary>

```bash
docker stop life-network-container 2>/dev/null && docker rm life-network-container 2>/dev/null
docker build -t life-network-image .
docker run -d --name life-network-container -v $(pwd)/logs:/app/logs life-network-image
```

> 재시작:

```bash
docker start life-network-container
```

</details>

---

## 봇 업데이트

<details>
<summary><strong>🔄 Git 설치자용</strong></summary>

```bash
cd life-network
git pull origin main
npm install
```

</details>

<details>
<summary><strong>🐳 Docker 사용자용</strong></summary>

```bash
docker stop life-network-container
docker rm life-network-container
docker build -t life-network-image .
docker run -d --name life-network-container life-network-image
```

</details>

---

## 문의 & 지원

* **추천 링크로 지원하기:** [Referral 링크](https://airdrop.lifenetworks.io?ref=ZIIPN)
* **후원:** [후원하기](https://t.me/KeoAirDropFreeNe/312/27801)
* **업무 관련 문의:** [@MeoMunDep](https://t.me/MeoMunDep)
* **지원 그룹:** [참여하기](https://t.me/KeoAirDropFreeNe)
* **업데이트 채널:** [채널 보기](https://t.me/KeoAirDropFreeNee)
* **YouTube:** [바로가기](https://www.youtube.com/@keoairdropfreene)
* **Instagram:** [팔로우](https://www.instagram.com/meomundep)
* **Tiktok:** [팔로우](https://www.tiktok.com/@meomundep)

---

⚠️ **면책조항**: 이 코드는 어떠한 보증 없이 “있는 그대로” 제공됩니다. 사용으로 인해 발생하는 모든 책임은 사용자에게 있습니다. 이 코드를 재판매 또는 어떤 형태로든 재배포하는 행위는 엄격히 금지됩니다.

✨ 봇을 사용해 주셔서 감사합니다. 스크립트를 통해 좋은 수익 얻길 바랍니다! 행운을 빕니다! 🚀
