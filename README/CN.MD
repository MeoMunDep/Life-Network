### 🚀 life-network 机器人安装指南

欢迎使用本机器人安装指南！请按照以下步骤正确安装和配置机器人。本指南专为新用户编写，内容清晰易懂。

📱 **手机用户（Termux）:** [点击此处查看指南](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## 目录

1. [系统要求](#系统要求)
2. [安装机器人](#安装机器人)
3. [机器人配置](#机器人配置)
4. [运行机器人](#运行机器人)
5. [更新机器人](#更新机器人)
6. [联系方式与支持](#联系方式与支持)

---

## 系统要求

在运行机器人之前，请确保已安装以下组件：

* **Node.js**（版本：`22.11.0`）
* **npm**（版本：`10.9.0`）
* **Git**
* **Docker** *(可选)*

📥 **Node.js & npm:** [下载链接](https://t.me/KeoAirDropFreeNe/257/1462)
📥 **Git:** [下载链接](https://t.me/KeoAirDropFreeNe/257/60831)

---

## 安装机器人

<details>
<summary><strong>🔧 通过 Git 安装</strong></summary>

```bash
git clone https://github.com/MeoMunDep/life-network.git
cd life-network
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger bs58 @solana/web3.js tweetnacl
```

</details>

<details>
<summary><strong>🧰 手动安装</strong></summary>

1. 手动下载并解压机器人文件。
2. 运行上面相同的 `npm install` 命令。

</details>

<details>
<summary><strong>🐳 使用 Docker 安装</strong></summary>

```bash
docker build -t life-network-image .
docker run -d --name life-network-container -v $(pwd)/logs:/app/logs life-network-image
```

> 💡 在 **Windows CMD** 中使用 `%cd%` 替代 `$(pwd)`

</details>

---

## 机器人配置

<details open>
<summary><strong>📜 1. <code>configs.json</code> - 主配置文件</strong></summary>

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

| **参数名称**                      | **类型**             | **默认值**  | **说明**           |
| ----------------------------- | ------------------ | -------- | ---------------- |
| `rotateProxy`                 | `boolean`          | `false`  | 是否在账户间轮换代理       |
| `proxyMode`                   | `string`           | `static` | 设置代理模式           |
| `skipInvalidProxy`            | `boolean`          | `false`  | 跳过无效代理           |
| `proxyRotationInterval`       | `number`           | `2`      | 代理轮换间隔（分钟）       |
| `delayEachAccount`            | `[number, number]` | `[5, 8]` | 每个账户之间的延迟（秒）     |
| `timeToRestartAllAccounts`    | `number`           | `300`    | 重新启动所有账户的间隔时间（秒） |
| `howManyAccountsRunInOneTime` | `number`           | `100`    | 同时运行的账户数量        |
| `doTasks`                     | `boolean`          | `true`   | 是否执行主要任务         |
| `connectWallets`              | `boolean`          | `true`   | 是否连接 Solana 钱包   |
| `bindReferralCodes`           | `boolean`          | `true`   | 是否绑定推荐码          |
| `referralCodes`               | `string[]`         | `[""]`   | 推荐码（可选）          |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> - 用户数据</strong></summary>

📥 [Telegram 获取指南](https://t.me/KeoAirDropFreeNee/1586)

```txt
ey...
ey...
ey...
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> - 代理列表</strong></summary>

📥 [免费代理来源 Webshare](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
...
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> - 钱包列表</strong></summary>

📥 [生成钱包](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
solana privatekey
solana privatekey
solana privatekey
...
```

</details>

---

## 运行机器人

<details open>
<summary><strong>🪟 在 Windows 上运行 (.bat)</strong></summary>

1. 双击 `run.bat`
2. 脚本会自动更新、安装依赖并启动机器人。

> 若运行失败，请右键 → **以管理员身份运行**
> 或通过命令行运行：

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 在 Linux/macOS 上运行 (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 使用 Docker 运行</strong></summary>

```bash
docker stop life-network-container 2>/dev/null && docker rm life-network-container 2>/dev/null
docker build -t life-network-image .
docker run -d --name life-network-container -v $(pwd)/logs:/app/logs life-network-image
```

> 后续重启命令：

```bash
docker start life-network-container
```

</details>

---

## 更新机器人

<details>
<summary><strong>🔄 如果通过 Git 安装</strong></summary>

```bash
cd life-network
git pull origin main
npm install
```

</details>

<details>
<summary><strong>🐳 如果使用 Docker</strong></summary>

```bash
docker stop life-network-container
docker rm life-network-container
docker build -t life-network-image .
docker run -d --name life-network-container life-network-image
```

</details>

---

## 联系方式与支持

* **支持我通过** [推荐链接](https://airdrop.lifenetworks.io?ref=ZIIPN)
* **捐赠:** [点击这里捐赠](https://t.me/KeoAirDropFreeNe/312/27801)
* **工作联系:** [@MeoMunDep](https://t.me/MeoMunDep)
* **支持群组:** [加入群组](https://t.me/KeoAirDropFreeNe)
* **更新频道:** [查看频道](https://t.me/KeoAirDropFreeNee)
* **YouTube:** [观看视频](https://www.youtube.com/@keoairdropfreene)
* **Instagram:** [关注我](https://www.instagram.com/meomundep)
* **Tiktok:** [关注我](https://www.tiktok.com/@meomundep)

---

⚠️ **免责声明**: 此代码按“原样”提供，不提供任何保证。使用本代码风险自负。严禁以任何形式出售或重新分发此代码。

✨ 感谢使用本机器人，祝你在空投中取得好成绩！🚀
