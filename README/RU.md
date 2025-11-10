### 🚀 Руководство по установке бота life-network

Добро пожаловать в руководство по установке бота! Следуйте инструкциям ниже, чтобы правильно установить и настроить бота. Это руководство предназначено для новых пользователей и содержит понятные объяснения для каждого шага.

📱 **Для мобильных пользователей (Termux):** [Посмотреть руководство здесь](https://github.com/MeoMunDep/Guides-for-using-my-script-on-termux)

---

## Содержание

1. [Системные требования](#системные-требования)
2. [Установка бота](#установка-бота)
3. [Настройка бота](#настройка-бота)
4. [Запуск бота](#запуск-бота)
5. [Обновление бота](#обновление-бота)
6. [Контакты и поддержка](#контакты-и-поддержка)

---

## Системные требования

Перед запуском убедитесь, что установлены:

* **Node.js** (версия: `22.11.0`)
* **npm** (версия: `10.9.0`)
* **Git**
* **Docker** *(опционально)*

📥 **Node.js и npm:** [Скачать](https://t.me/KeoAirDropFreeNe/257/1462)
📥 **Git:** [Скачать](https://t.me/KeoAirDropFreeNe/257/60831)

---

## Установка бота

<details>
<summary><strong>🔧 Установка через Git</strong></summary>

```bash
git clone https://github.com/MeoMunDep/life-network.git
cd life-network
npm install --no-audit --no-fund --prefer-offline --force user-agents axios meo-forkcy-colors meo-forkcy-utils meo-forkcy-proxy meo-forkcy-logger bs58 @solana/web3.js tweetnacl
```

</details>

<details>
<summary><strong>🧰 Ручная установка</strong></summary>

1. Скачайте и распакуйте архив с ботом.
2. Выполните ту же команду `npm install`, что указана выше.

</details>

<details>
<summary><strong>🐳 Установка с помощью Docker</strong></summary>

```bash
docker build -t life-network-image .
docker run -d --name life-network-container -v $(pwd)/logs:/app/logs life-network-image
```

> 💡 В **Windows CMD** используйте `%cd%` вместо `$(pwd)`

</details>

---

## Настройка бота

<details open>
<summary><strong>📜 1. <code>configs.json</code> — Основная конфигурация</strong></summary>

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

| **Параметр**                  | **Тип**           | **По умолчанию** | **Описание**                                 |
| ----------------------------- | ----------------- | ---------------- | -------------------------------------------- |
| `rotateProxy`                 | `boolean`         | `false`          | Включить ротацию прокси между аккаунтами     |
| `proxyMode`                   | `string`          | `static`         | Режим работы прокси                          |
| `skipInvalidProxy`            | `boolean`         | `false`          | Пропускать аккаунты с нерабочим прокси       |
| `proxyRotationInterval`       | `number`          | `2`              | Интервал ротации прокси (в минутах)          |
| `delayEachAccount`            | `[number,number]` | `[5,8]`          | Случайная задержка между аккаунтами (в сек.) |
| `timeToRestartAllAccounts`    | `number`          | `300`            | Перезапуск всех аккаунтов каждые N секунд    |
| `howManyAccountsRunInOneTime` | `number`          | `100`            | Количество одновременно работающих аккаунтов |
| `doTasks`                     | `boolean`         | `true`           | Выполнять основные задания                   |
| `connectWallets`              | `boolean`         | `true`           | Подключать Solana-кошельки                   |
| `bindReferralCodes`           | `boolean`         | `true`           | Привязывать реферальные коды                 |
| `referralCodes`               | `string[]`        | `[""]`           | Список реферальных кодов                     |

</details>

<details>
<summary><strong>🗂️ 2. <code>datas.txt</code> — Данные пользователей</strong></summary>

📥 [Инструкция с Telegram](https://t.me/KeoAirDropFreeNee/1586)

```txt
ey...
ey...
ey...
```

</details>

<details>
<summary><strong>🌐 3. <code>proxies.txt</code> — Список прокси</strong></summary>

📥 [Бесплатные прокси с Webshare](https://www.webshare.io/?referral_code=4l5kb3glsce7)

```txt
host:port
http://host:port
socks5://user:pass@host:port
...
```

</details>

<details>
<summary><strong>💼 4. <code>wallets.txt</code> — Список кошельков</strong></summary>

📥 [Сгенерировать кошельки здесь](https://github.com/MeoMunDep/Automatic-Ultimate-Create-Wallets-for-Airdrop)

```txt
solana privatekey
solana privatekey
solana privatekey
...
```

</details>

---

## Запуск бота

<details open>
<summary><strong>🪟 Windows (.bat)</strong></summary>

1. Дважды кликните `run.bat`
2. Скрипт автоматически обновит файлы, установит зависимости и запустит бота.

> Если не запускается — кликните правой кнопкой → **Запуск от имени администратора**
> Или запустите через CMD:

```cmd
run.bat
```

</details>

<details>
<summary><strong>🐧 Linux/macOS (.sh)</strong></summary>

```bash
chmod +x run.sh
./run.sh
```

</details>

<details>
<summary><strong>🐳 Docker</strong></summary>

```bash
docker stop life-network-container 2>/dev/null && docker rm life-network-container 2>/dev/null
docker build -t life-network-image .
docker run -d --name life-network-container -v $(pwd)/logs:/app/logs life-network-image
```

> Чтобы перезапустить позже:

```bash
docker start life-network-container
```

</details>

---

## Обновление бота

<details>
<summary><strong>🔄 Если установлен через Git</strong></summary>

```bash
cd life-network
git pull origin main
npm install
```

</details>

<details>
<summary><strong>🐳 Если используется Docker</strong></summary>

```bash
docker stop life-network-container
docker rm life-network-container
docker build -t life-network-image .
docker run -d --name life-network-container life-network-image
```

</details>

---

## Контакты и поддержка

* **Поддержите меня через** [реферальную ссылку](https://airdrop.lifenetworks.io?ref=ZIIPN)
* **Донат:** [Пожертвовать здесь](https://t.me/KeoAirDropFreeNe/312/27801)
* **Рабочие контакты:** [@MeoMunDep](https://t.me/MeoMunDep)
* **Группа поддержки:** [Присоединиться](https://t.me/KeoAirDropFreeNe)
* **Канал обновлений:** [Посмотреть](https://t.me/KeoAirDropFreeNee)
* **YouTube:** [Смотреть](https://www.youtube.com/@keoairdropfreene)
* **Instagram:** [Подписаться](https://www.instagram.com/meomundep)
* **Tiktok:** [Подписаться](https://www.tiktok.com/@meomundep)

---

⚠️ **Отказ от ответственности**: Код предоставляется "как есть", без каких-либо гарантий. Используйте на свой риск. Перепродажа или распространение кода в любом виде строго запрещено.

✨ Спасибо за использование бота! Удачи в заработке на airdrop! 🚀
