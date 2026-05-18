# KuroBails

Modern & Lightweight WhatsApp Web API Library

---

## Installation

```bash
npm install github:nawwtech/kurobails
```

## Dependencies

```json
"dependencies": {
  "kurobails": "github:nawwtech/kurobails"
}
```

---

# Import

```javascript
const {
  default: makeKuroSocket
} = require("kurobails")
```

---

# Authentication

## QR Login

```javascript
const {
  default: makeKuroSocket
} = require("kurobails")

const client = makeKuroSocket({
  browser: ["Kuro", "Chrome", "1.0.0"],
  printQRInTerminal: true
})
```

---

## Pairing Login

```javascript
const {
  default: makeKuroSocket,
  fetchLatestWAWebVersion
} = require("kurobails")

const client = makeKuroSocket({
  browser: ["Kuro", "Chrome", "1.0.0"],
  printQRInTerminal: false,
  version: fetchLatestWAWebVersion()
})

const code =
await client.requestPairingCode("628xxxx")

console.log("Pairing Code:", code)
```

---

# Basic Messages

## Send Text

```javascript
await client.sendText(
  m.chat,
  "KuroBails Connected"
)
```

---

## Send Image

```javascript
await client.sendImage(
  m.chat,
  { url: "./kuro.jpg" },
  "Kuro Image"
)
```

---

## Send Video

```javascript
await client.sendVideo(
  m.chat,
  { url: "./kuro.mp4" },
  "Kuro Video"
)
```

---

## Send Audio

```javascript
await client.sendAudio(
  m.chat,
  { url: "./kuro.mp3" }
)
```

---

## Send Poll

```javascript
await client.sendPoll(
  m.chat,
  "Kuro Poll",
  ["Yes", "No"],
  true
)
```

---

# Advanced Messages

## Order Message

```javascript
await client.sendMessage(m.chat, {
  message: "Kuro Store",
  orderTitle: "Kuro Corporation",
  totalAmount1000: 25000,
  totalCurrencyCode: "IDR"
})
```

---

## Product Message

```javascript
await client.relayMessage(m.chat, {
  productMessage: {
    title: "KuroFile.pdf",
    description: "Kuro Product Message",
    productId: "KURO-ID",
    retailerId: "KURO-STORE",
    currencyCode: "IDR",
    priceAmount1000: 10000
  }
})
```

---

## Poll Snapshot

```javascript
await client.sendMessage(m.chat, {
  pollResultMessage: {
    name: "Kuro Poll",
    options: [
      {
        optionName: "Option One"
      },
      {
        optionName: "Option Two"
      }
    ]
  }
})
```

---

# Group Features

## Group Label

```javascript
await client.sendMessage(m.chat, {
  groupLabel: {
    labelText: "Kuro Group"
  }
})
```

---

## Mention Members

```javascript
await client.sendMessageMembers(
  m.chat,
  {
    extendedTextMessage: {
      text: "Hello Members"
    }
  },
  {}
)
```

---

## Status Mention

```javascript
await client.statusMention(
  m.chat,
  {
    extendedTextMessage: {
      text: "KuroBails"
    }
  }
)
```

---

# Features

- Multi Device Support
- Lightweight Performance
- Fast Socket Connection
- Custom Message Support
- Easy Integration
- TypeScript Support

---

# Credits

- WhiskeySockets
- Baileys
- Kuro Developer

---

# Community

https://t.me/blavouchnaww