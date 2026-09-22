# 🤖 Robot mobil cu monitorizare video și control prin interfață web

Proiect realizat pentru monitorizare video în timp real, detectarea automată a mișcării și transmiterea notificărilor la distanță.

## 📌 Despre proiect

Proiectul constă în realizarea unui sistem de monitorizare bazat pe **ESP32-CAM**, senzori **PIR** și o interfață web.

Sistemul utilizează **4 module ESP32-CAM**, fiecare având asociat un senzor PIR pentru detectarea mișcării. Atunci când este detectată mișcare, camera realizează automat o fotografie și o transmite către un bot **Telegram**, împreună cu identificarea camerei care a detectat evenimentul.

În paralel, cele patru fluxuri video pot fi urmărite simultan prin intermediul unei interfețe web.

## ✨ Funcționalități

- 📷 4 camere ESP32-CAM
- 🎥 Streaming video în timp real
- 👁️ Detectarea mișcării cu senzori PIR
- 📸 Captură automată la detectarea mișcării
- 📱 Notificări și fotografii prin Telegram
- 🌐 Interfață web pentru monitorizarea celor 4 camere
- 📡 Comunicare prin Wi-Fi
- 🔄 Monitorizare simultană a celor patru camere

## 🧩 Componente hardware

| Componentă | Cantitate |
|---|---:|
| ESP32-CAM | 4 |
| Senzor PIR HC-SR501 | 4 |
| Platformă robot mobil | 1 |
| Motoare DC | 2 |
| Driver motoare | 1 |
| Acumulator / baterie | 1 |
| Fire de conexiune | Mai multe |

## 🔌 Conexiunea ESP32-CAM – PIR

Fiecare senzor PIR este conectat la modulul ESP32-CAM astfel:

| PIR | ESP32-CAM |
|---|---|
| VCC | 5V |
| GND | GND |
| OUT | GPIO3 (U0R) |

> **Notă:** GPIO3 este utilizat pentru semnalul senzorului PIR. În timpul programării ESP32-CAM, conexiunea OUT a senzorului PIR trebuie deconectată.

## 💻 Software

Proiectul utilizează:

- **Arduino IDE** – programarea modulelor ESP32-CAM
- **C/C++** – dezvoltarea programului pentru ESP32
- **HTML / CSS / JavaScript** – interfața web
- **Telegram Bot API** – transmiterea notificărilor și imaginilor
- **Wi-Fi** – comunicarea dintre componente și interfața de monitorizare

## 🌐 Interfața web

Interfața web afișează cele patru camere într-o structură **2×2**, fiecare cameră având propriul flux video.

```text
┌─────────────────────┬─────────────────────┐
│      CAMERA 1       │      CAMERA 2       │
│      📷 LIVE        │      📷 LIVE        │
├─────────────────────┼─────────────────────┤
│      CAMERA 3       │      CAMERA 4       │
│      📷 LIVE        │      📷 LIVE        │
└─────────────────────┴─────────────────────┘