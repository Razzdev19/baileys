# WhatsApp Baileys Xynoz

<p align="center">
  <img src="https://files.catbox.moe/369pux.jpg" alt="Thumbnail" />
</p>

WhatsApp Baileys adalah pustaka sumber terbuka yang dirancang untuk membantu pengembang membangun solusi otomatisasi dan integrasi dengan WhatsApp secara efisien dan langsung. Menggunakan teknologi websocket tanpa memerlukan browser, pustaka ini mendukung berbagai fitur seperti manajemen pesan, penanganan obrolan, administrasi grup, serta pesan interaktif dan tombol aksi untuk pengalaman pengguna yang lebih dinamis.

Dikembangkan dan dipelihara secara aktif, Baileys terus menerima pembaruan untuk meningkatkan stabilitas dan kinerja. Salah satu fokus utamanya adalah meningkatkan proses pemasangan dan otentikasi agar lebih stabil dan aman. Fitur pemasangan dapat disesuaikan dengan kode Anda sendiri, membuat proses lebih andal dan kurang rentan terhadap gangguan.

Pustaka ini sangat cocok untuk membangun bot bisnis, sistem otomatisasi obrolan, solusi layanan pelanggan, dan berbagai aplikasi otomatisasi komunikasi lainnya yang membutuhkan stabilitas tinggi dan fitur komprehensif. Dengan desain yang ringan dan modular, Baileys mudah diintegrasikan ke dalam berbagai sistem dan platform.
---

### Fitur dan Keunggulan Utama

- Mendukung proses pemasangan otomatis dan kustom
- Memperbaiki masalah pemasangan sebelumnya yang sering menyebabkan kegagalan atau pemutusan koneksi
- Mendukung pesan interaktif, tombol aksi, dan menu dinamis
- Manajemen sesi otomatis yang efisien untuk pengoperasian yang andal
- Kompatibel dengan fitur multi-perangkat terbaru dari WhatsApp
- Ringan, stabil, dan mudah diintegrasikan ke berbagai sistem
- Cocok untuk mengembangkan bot, otomatisasi, dan solusi komunikasi lengkap
- Dokumentasi komprehensif dan contoh kode untuk mempermudah pengembangan
---

## Spesial Thanks For Kayzen

## Memulai

Mulailah dengan menginstal pustaka melalui pengelola paket pilihan Anda, lalu ikuti panduan konfigurasi yang disediakan. Anda juga dapat menggunakan kode contoh yang sudah jadi untuk memahami cara kerja fitur-fiturnya. Gunakan penyimpanan sesi dan fitur perpesanan interaktif untuk membangun solusi lengkap dan stabil yang disesuaikan dengan kebutuhan bisnis atau proyek Anda.
## Cara memakai?
```json
"depencies": {
  "@whiskeysockets/baileys": "github:Xynoz-Xnoz/baileys"
}
```
## Import
```javascript
const {
  default:makeWASocket,
  // Other Options 
} = require('@whiskeysockets/baileys');
```

---
# Cara connect ke whatsapp
## Dengan QR Code
```javascript
const {
  default: makeWASocket
} = require('@whiskeysockets/baileys');

const client = makeWASocket({
  browser: ['Ubuntu', 'Chrome', '20.00.1'],
  printQRInTerminal: true
})
```

## Connect dengan nomor
```javascript
const {
  default: makeWASocket,
  fetchLatestWAWebVersion
} = require('@whiskeysockets/baileys');

const client = makeWASocket({
  browser: ['Ubuntu', 'Chrome', '20.00.1'],
  printQRInTerminal: false,
  version: fetchLatestWAWebVersion()
  // Other options
});

const number = "628XXXXX";
const code = await client.requestPairingCode(number.trim) /* Use : (number, "YYYYYYYY") for custom-pairing */

console.log("Ur pairing code : " + code)
```

# Mengirim Pesan

## Mengirim orderMessage
```javascript
const fs = require('fs');
const nameImg = fs.readFileSync('./YourImage');

await client.sendMessage(m.chat, {
  thumbnail: YourImg,
  message: "Gotta get a grip",
  orderTitle: "HaveANiceDay",
  totalAmount1000: 8888,
  totalCurrencyCode: "IDR"
}, { quoted:m })
```

## Mengirim pollResultSnapshotMessage
```javascript
await client.sendMessage(m.chat, {
  pollResultMessage: {
    name: "n",
    options: [
      {
        optionName: "poll 1"
      },
      {
        optionName: "poll 2"
      }
    ],
    newsletter: {
      newsletterName: "Xynozdev",
      newsletterJid: "1@newsletter"
    }
  }
})
```

## Mengirim productMessage
```javascript
await client.relayMessage(m.chat, {
  productMessage {
    title: "",
    description: "zZZ...",
    thumbnail: { url: "./YourImage" },
    productId: "EXAMPLE_TOKEN",
    retailerId: "EXAMPLE_RETAILER_ID",
    url: "https://t.me/xynozdev",
    body: "Nak Tido",
    footer: "Footer",
    buttons: [
      {
        name: "cta_url",
        buttonParamsJson: "{\"display_text\":\"Xynoz\",\"url\":\"https://t.me/xynozdev\"}"
      }
    ],
    priceAmount1000: 72502,
    currencyCode: "IDR"
  }
})
```
## Thanks For Support
```javascript
const thanksFor = async () => {
  const credit = new Map([
    ["kayzen", ""],
    ["Gupong", "source my fork"],
    ["yuukey", "main source baileys ( maybe )"]
  ]);

  return Object.fromEntries(credit);
};
```


