
# Baileys-Duplicated
![Baileys-Duplicated](https://raw.githubusercontent.com/Viper-x0/Viper-X0/refs/heads/main/lib/logo.png)

---
# Baileys Duplicated
---

> **Baileys-Duplicated** is a customized fork of the [Baileys](https://github.com/WhiskeySockets/Baileys) WhatsApp Web API. Built upon the incredible foundations laid by **adiwajshing** and actively maintained by the **WhiskeySockets** team, this version extends functionality with additional features and enhanced support for bot developers.

---

## Install

Use the stable version:

```
npm i baileys-duplicated
```

>import
```ts 
import makeWASocket from 'baileys-duplicated'
```
> or
```js
const { makeWASocket } = require('baileys-duplicated')
```


---

## Features

---

### 1. Button Message Support

Send Button messages.

```js
const buttons = [
  { buttonId: 'id1', buttonText: { displayText: 'Button 1' }, type: 1 },
  { buttonId: 'id2', buttonText: { displayText: 'Button 2' }, type: 1 }
];

const buttonMessage = {
  text: "Hi, it's a button message",
  footer: 'Hello World',
  buttons,
  headerType: 1,
  viewOnce: true
};

await sock.sendMessage(jid, buttonMessage, { quoted: null });
```

---

### 2. List Message Support

Send interactive messages to enhance user engagement.

```js

const { generateWAMessageFromContent, proto } = require('baileys-duplicated');

const message = await generateWAMessageFromContent(jid, {
  viewOnceMessage: {
    message: {
      messageContextInfo: {
        deviceListMetadata: {},
        deviceListMetadataVersion: 2
      },
      interactiveMessage: proto.Message.InteractiveMessage.create({
        body: { text: "Hi, it's a list message" },
        footer: { text: "Hello World!" },
        header: {
          title: "Hello",
          subtitle: "test",
          hasMediaAttachment: false
        },
        nativeFlowMessage: {
          buttons: [
            {
              name: "single_select",
              buttonParamsJson: JSON.stringify({
                title: "List message",
                sections: [{
                  menu: "hhhh",
                  highlight_label: "label",
                  rows: [
                    { header: "header", title: "title 1", description: "description 1", id: "id1" },
                    { header: "header", title: "title 2", description: "description 2", id: "id2" }
                  ]
                }]
              })
            },
            {
              name: "cta_url",
              buttonParamsJson: JSON.stringify({
                display_text: "Url",
                url: "https://devstackx.in",
                merchant_url: "https://devstackx.in"
              })
            },
            {
              name: "quick_reply",
              buttonParamsJson: JSON.stringify({
                display_text: "Quick Reply",
                id: "mm"
              })
            },
            {
              name: "cta_call",
              buttonParamsJson: JSON.stringify({
                display_text: "Call",
                id: "message"
              })
            },
            {
              name: "cta_copy",
              buttonParamsJson: JSON.stringify({
                display_text: "Copy",
                id: "123456789",
                copy_code: "message"
              })
            },
            {
              name: "cta_reminder",
              buttonParamsJson: JSON.stringify({
                display_text: "Reminder",
                id: "message"
              })
            },
            {
              name: "cta_cancel_reminder",
              buttonParamsJson: JSON.stringify({
                display_text: "Cancel Reminder",
                id: "message"
              })
            },
            {
              name: "address_message",
              buttonParamsJson: JSON.stringify({
                display_text: "Address",
                id: "message"
              })
            },
            {
              name: "send_location",
              buttonParamsJson: JSON.stringify({
                display_text: "Location",
                id: "location_id"
              })
            }
          ]
        }
      })
    }
  }
}, {});

await sock.relayMessage(message.key.remoteJid, message.message, { messageId: message.key.id });
```

---

## Credits

- [`@adiwajshing`](https://github.com/adiwajshing) – *Author of the Baileys library*
- [`WhiskeySockets`](https://github.com/WhiskeySockets/Baileys) – *Current maintainers of the Baileys codebase*

---

## Project Contributors


| Name           | GitHub                                 |
|----------------|----------------------------------------|
| ![@Viper-x0](https://github.com/Viper-X0.png?size=50) | [Viper-x0](https://github.com/Viper-X0) |
| ![@Lord-Official](https://github.com/Lord-Official.png?size=50) | [Lord-Official](https://github.com/Lord-Official) |
| ![@KichuExe](https://github.com/KichuExe.png?size=50) | [KichuExe](https://github.com/KichuExe) |

> Big thanks to all contributors for helping evolve this project into a more powerful and flexible tool.

---

