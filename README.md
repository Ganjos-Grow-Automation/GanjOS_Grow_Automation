# 🌱 GanjOS Grow Automation

> ⚠️ **Legal Disclaimer**
>
> This project is intended solely for legal plant cultivation, automation and environmental monitoring. We **do not** encourage or support any illegal activity.
>
> Users are solely responsible for ensuring that the use of GanjOS complies with the **local laws and regulations** of their country, state or region.
>
> The developers assume **no liability** for unlawful use, misuse, damages, or any consequences resulting from the use of this software or related hardware.
>
> When in doubt, please consult a **legal expert familiar with IT and cultivation law** in your jurisdiction.


**Language / Sprache:**  
🇩🇪 [Deutsch anzeigen](#ganjos-grow-automation-deutsch)  
🇬🇧 [View in English](#ganjos-grow-automation-english)

---

## 🇩🇪 GanjOS Grow Automation (Deutsch) {#ganjos-grow-automation-deutsch}
<details>
<summary>▶️ Klicke hier, um mehr über GanjOS zu erfahren</summary>

### 📚 Inhaltsverzeichnis

- [🔧 Was ist GanjOS?](#was-ist-ganjos)
- [🖼️ Preview & Beispiel-Setup](#preview--beispiel-setup)
- [🧩 Module & Komponenten](#module--komponenten)
- [🚧 Roadmap / Geplante Features](#roadmap--geplante-features)
- [🛠 Installation & Anleitungen](#installation--anleitungen)
- [🤝 Mitmachen & Mitwirken](#mitmachen--mitwirken)
- [📄 Lizenz](#lizenz)
- [🧑‍💻 Autoren & Community](#autoren--community)
- [🌐 Sponsoren & Inspiration](#sponsoren--inspiration)


## 🔧 Was ist GanjOS? {#was-ist-ganjos}

> ⚠️ **Beta-Hinweis:**  
> GanjOS befindet sich aktuell in der **Beta-Phase** – Fehler, fehlende Funktionen und Änderungen sind noch möglich.

**GanjOS** ist ein Community-basiertes Open-Source-Projekt zur Automatisierung von Indoor-Grow-Umgebungen.  
Es wurde ins Leben gerufen, um Growern eine **kostengünstige und datengestützte Möglichkeit** zu bieten, ihren Grow mit etwas Eigeninitiative zu **automatisieren, zu überwachen und optimal zu steuern**.

Das System basiert auf [**Home Assistant**](https://www.home-assistant.io/) – einer leistungsstarken Open-Source-Plattform für Heimautomatisierung, die es ermöglicht, verschiedenste Sensoren, Aktoren und Datenquellen zu verbinden, zu visualisieren und zu automatisieren.

Durch die Kombination mit zusätzlichen Home Assistant Add-ons (z. B. ESPHome, MQTT, Node-RED) ermöglicht GanjOS:
- die Anbindung günstiger DIY-Hardware (z. B. ESP32-Platinen)
- die kontinuierliche **Erfassung von Umweltdaten** (Temperatur, Luftfeuchtigkeit, CO₂, Licht, Bodenwerte)
- die **automatische Steuerung** von Licht, Klima, Ventilation, Bewässerung
- die **dokumentierte Auswertung** deines Grows über beliebige Zeiträume

Sobald Daten über Home Assistant ausgelesen werden können, können sie auch in GanjOS eingebunden, verarbeitet und visualisiert werden.

---

### 📱 Folge GanjOS für Updates, Tipps & Community-Insights:

- 🌍 Website: [ganjos.io](https://ganjos.io)
- 📲 Instagram: [@ganjos.official](https://www.instagram.com/ganjos.official)  
- 🧪 Lab-Projekt: [@ganjos.lab](https://www.instagram.com/ganjos.lab)  
- 🔗 Linkspace Übersicht: [link.space/@ganjosgrowautomation](https://link.space/@ganjosgrowautomation)


## 🖼️ Preview & Beispiel-Setup (mit Hardwareliste) {#preview--beispiel-setup}

GanjOS zeigt seine Stärken in der Praxis: Eine zentrale Oberfläche für alle Bereiche deiner Grow-Umgebung – von VPD-basierten Klimadaten bis hin zur Licht- und Bewässerungssteuerung.

Das folgende Beispiel-Setup zeigt:
- Ein Growroom mit ESP32-Sensorik und Aktoren
- VPD-Visualisierung und Abweichungsanalyse
- Steuerbare Licht- & Klimageräte mit Echtzeitdaten
- Ein modulares Dashboard mit verschiedenen Bereichen & Stadien

<details>
<summary>📸 Screenshots anzeigen</summary>

![Dashboard 1](https://github.com/user-attachments/assets/ddf5a8eb-5d33-4348-8c36-1cb051d0e90e)
![Dashboard 2](https://github.com/user-attachments/assets/2afe4348-411e-4719-bee6-292ee979a8a4)
![Dashboard 3](https://github.com/user-attachments/assets/a660bdb6-b177-47de-9349-2e881c453ad8)
![Dashboard 4](https://github.com/user-attachments/assets/e07214e1-4957-42bc-aa66-bc48d1135835)

</details>

<details>
<summary>🧰 Beispielhafte Hardware für ein 3-Pflanzen-Setup</summary>

**Grow-Bereich:**

- 🌱 **Grow-Zelt**: [`Eden Growbox 110x60x180`](https://www.eden-grow.de/growshop/growboxen/eden-growbox-110-60-80/)
- 💡 **LED-Leuchte**: [`2x SANlight EVO 3-60 inkl. Dimmerkabel`](https://amzn.to/4jlt9Bk) *(Affiliate-Link – du zahlst nicht mehr, unterstützt aber das Projekt)*
- 🌬️ **Umluftventilator**: [`AC Infinity Cloudray S6`](https://amzn.to/43gzCZL) *(Affiliate-Link)*
- 🌫️ **Luftbefeuchter**: [`RAM Luftbefeuchter 13L`](https://amzn.to/4dx7x3L) *(Affiliate-Link)*
- 🌀 **Abluftsystem**: [`Prima Klima EC BLUE 125mm`](https://www.eden-grow.de/growshop/klimatechnik/prima-klima-ec-ventilator-blue-680m3-h-125mm-rj45/)  
  → *Hinweis: Aktivkohlefilter wird empfohlen*
- 🧵 **Living Soil Stofftöpfe**: [`Living Soil Beet MSL 100x50x50`](https://truesoil.at/products/living-soil-beet)  
  → *Mit dem Code „GanjOS“ gibt’s exklusiven Rabatt*

---

**Sensorik & Steuerung:**

> [!IMPORTANT]  
> Dieses Beispiel zeigt ein minimalistisches, aber stabiles Setup. Fokus liegt auf Klimasteuerung – Bodenwerte werden nicht digital erfasst (z. B. bei Nutzung von Blumat).

- 📟 **ESP32-Board**: [`FireBeetle 2 ESP32-E`](https://www.dfrobot.com/product-2231.html?tracking=WjyQJqF2zJKV41fDEVNqlL8iIoSaXJXcs510uBhCzQJ0RftedpYAlvGH8TibE7eY) *(Affiliate-Link)*
- 📟 **IO Shield**: [`DFRobot IO Expansion Shield für FireBeetle 2`](https://www.dfrobot.com/product-2395.html?tracking=WjyQJqF2zJKV41fDEVNqlL8iIoSaXJXcs510uBhCzQJ0RftedpYAlvGH8TibE7eY) *(Affiliate-Link)*

- 🌡️ **Sensoren**:
  - [`SHT31 Temperatur/Luftfeuchte`](https://www.dfrobot.com/product-2160.html?tracking=WjyQJqF2zJKV41fDEVNqlL8iIoSaXJXcs510uBhCzQJ0RftedpYAlvGH8TibE7eY) *(Affiliate-Link)*
  - [`ENS160 CO₂ / TVOC`](https://www.dfrobot.com/product-2623.html?tracking=WjyQJqF2zJKV41fDEVNqlL8iIoSaXJXcs510uBhCzQJ0RftedpYAlvGH8TibE7eY) *(Affiliate-Link)*

- ⚡ **Funksteckdosen**: [`4x Shelly Smart Plug S`](https://amzn.to/3FjM8yo) *(Affiliate-Link – für alle Aktoren)*
- 🎛️ **Dimmer**: [`2x Shelly Dimmer 0-10V`](https://amzn.to/3ZtWBxR) *(Affiliate-Link – Licht & Abluft steuerbar)*

---

**Sonstiges:**

- 🔌 **Stromversorgung**: [`Rocoren USB-C Mehrfachladegerät`](https://amzn.to/4dxQgaL) *(Affiliate-Link)*
- 📦 **Gehäuse**: `IP68 Schutzdose für ESP32 Platinen` *(Platzhalter – bitte bei Bedarf ergänzen)*
- 🔗 **Verkabelung**: [`Anker USB-C Kabel`](https://amzn.to/4kmvKw4) *(Affiliate-Link)*

</details>

## 🧩 Module & Komponenten {#module--komponenten}

GanjOS ist modular aufgebaut. Das bedeutet: Du kannst einzelne Teile nutzen, kombinieren oder erweitern – je nach Setup, Hardware und Know-how.

| Modul | Beschreibung | Repository |
|-------|--------------|------------|
| 🧠 **Home Assistant Integration** | Zentrale Logik, Entitäten & Gerätesteuerung via ESP32 | [`GanjOS_hass_core`](https://github.com/Ganjos-Grow-Automation/GanjOS_hass_core) |
| 🖥️ **Dashboard Templates** | Vorbereitete Lovelace YAML-Setups für Home Assistant | [`GanjOS_hass_dashboard`](https://github.com/Ganjos-Grow-Automation/GanjOS_hass_dashboard) |
| 🔁 **Node-RED Flows** | Automatisierungen und Logiken als Node-RED-Vorlagen | [`GanjOS_NodeRED_Flows`](https://github.com/Ganjos-Grow-Automation/GanjOS_NodeRED_Flows) |
| 🎓 **Tutorials & Onlinekurs** | Guides & kostenpflichtige Schulungsinhalte *(in Planung)* | [ganjos.io/kurs](https://ganjos.io/kurs) |

## 🚧 Roadmap / Geplante Features {#roadmap--geplante-features}

GanjOS wird kontinuierlich weiterentwickelt – unser Ziel ist es, Grow-Automatisierung so intelligent, anpassbar und nutzerfreundlich wie möglich zu machen.  

Folgende Funktionen befinden sich derzeit in Planung oder Entwicklung:

- 🌿 **Crop Steering**: Dynamische Anpassung von Klima- und Lichtparametern basierend auf dem Entwicklungsstadium der Pflanze
- 🎛️ **Automatische Gerätesteuerung**: Prozentuale Dimmung von Geräten wie Abluft, Licht, Heiz- oder Luftbefeuchter – auf Basis von VPD und Zielwerten
- 🤖 **AI-gestützte Grow-Optimierung**: Einsatz von KI-Modellen zur intelligenten Steuerung und Vorhersage idealer Bedingungen
- 🧠 **Big Data Langzeitspeicherung**: Anonyme Erfassung und Aggregation von Sensordaten zur Erkennung von Mustern und Optimierungspotenzialen
- 🧺 **Automatisierter Drying-Prozess**: Geführte und automatisch geregelte Trocknungsphasen mit Sollwertanpassung je nach Fortschritt
- 🚨 **Erweitertes Alerting**: Flexible Benachrichtigungen bei Schwellenwertabweichungen, Trends oder Sensorfehlern (E-Mail, App, Discord etc.)

> 💡 Eine öffentliche Übersicht und Priorisierung der Roadmap findest du im  
> [📌 GitHub Project Board → GanjOS HA Integration](https://github.com/orgs/Ganjos-Grow-Automation/projects/6)

> 💬 Du hast eine Idee oder willst ein Feature vorschlagen?  
> 👉 Öffne gerne ein [GitHub Issue im Hauptrepository](https://github.com/Ganjos-Grow-Automation/GanjOS_Grow_Automation/issues)  
> oder diskutiere deinen Vorschlag im [Community Discord](https://discord.ganjos.io)

## 🛠 Installation & Anleitungen {#installation--anleitungen}

Die Installation von GanjOS erfolgt modular über verschiedene Teilbereiche:

| Komponente         | Beschreibung                                     | Anleitung                                    |
|--------------------|--------------------------------------------------|----------------------------------------------|
| 🔌 **Integration** | GanjOS Home Assistant Integration (Basis)        | [→ Zur Anleitung](https://github.com/Ganjos-Grow-Automation/GanjOS_hass_core) |
| 🖥️ **Dashboard**   | YAML-basierte UI-Vorlagen für Home Assistant     | [→ Dashboard Repo](https://github.com/Ganjos-Grow-Automation/GanjOS_hass_dashboard) |
| 🔁 **Node-RED**    | Automatisierungs-Logik als Flows (optional)      | [→ Node-RED Flows](https://github.com/Ganjos-Grow-Automation/GanjOS_NodeRED_Flows) |

> ℹ️ Für eine schnelle Grundinstallation genügt es, die Integration über HACS zu installieren und das Setup über den Home Assistant UI-Flow durchzuführen.

---

### 📂 Anschlusspläne & Sensor-Guides

Im Ordner [`./Guides`](./Guides) findest du beispielhafte Anschlusspläne und Verdrahtungen für unterstützte Sensoren und Hardware, inkl. passender ESPHome-Konfigurationen.

> ⚠️ **Haftungsausschluss:**  
> Wir übernehmen keinerlei Haftung für Anschlussfehler, Schäden an Geräten oder Folgeprobleme. Die bereitgestellten Informationen dienen ausschließlich zu Bildungszwecken.  
> Der Nachbau erfolgt auf eigene Verantwortung – bei Unsicherheiten kontaktiere bitte qualifiziertes Fachpersonal.

---

### 🎥 Videoanleitungen (bald verfügbar)

Ein vollständiges Einstiegstutorial wird demnächst auf unserem offiziellen [YouTube-Kanal](https://www.youtube.com/@ganjos.official) veröffentlicht.

Zudem arbeiten wir an **Premium-Tutorials**, die gezielt fortgeschrittene Themen behandeln, darunter:

- 📊 Wie man Sensorwerte je nach Pflanzenstadium gewichtet (z. B. VPD vs. CO₂)
- 🖼️ Möglichkeiten zur Individualisierung des Dashboards
- 🔁 Eigene Automatisierungen für spezifische Setups entwickeln
- 📈 Wie man aus Growdaten Trends & Handlungsempfehlungen ableiten kann

> 📌 Zugang zu Premium-Inhalten erhältst du zukünftig über unsere [Ko-Fi-Seite](https://ko-fi.com/ganjos)

## 📄 Lizenz {#lizenz}

GanjOS wird unter einem **Dual-Lizenz-Modell** veröffentlicht:

1. **Private und nicht-kommerzielle Nutzung**  
   → Erlaubt unter den Bedingungen der [MIT-Lizenz](./LICENSE)

2. **Kommerzielle Nutzung** (z. B. in Grow-Shops, Social Clubs oder SaaS-Angeboten)  
   → Erfordert eine kostenpflichtige Lizenz

> 📩 Für kommerzielle Lizenzanfragen kontaktiere uns bitte unter [info@ganjos.io](mailto:info@ganjos.io)

---

### ⚠️ Hinweis zur kommerziellen Nutzung

Die unlizenzierte kommerzielle Nutzung von GanjOS verstößt gegen die geltenden Lizenzbedingungen.  
In solchen Fällen behalten wir uns rechtliche Schritte sowie die Geltendmachung von Schadensersatz vor.

Bitte kontaktiere uns frühzeitig für eine rechtskonforme Lizenzierung:  
[info@ganjos.io](mailto:info@ganjos.io)

## 🤝 Mitmachen & Unterstützen {#mitmachen--unterstuetzen}

Wir freuen uns über jeden Beitrag – ob aktiv im Code, durch Ideen oder passiv durch Support. So kannst du GanjOS stärken:

---

### 🐛 Fehler melden & Feature-Ideen einreichen

- Entdecke einen Bug oder möchtest eine neue Funktion vorschlagen?  
  → Öffne ein [GitHub Issue im Hauptrepository](https://github.com/Ganjos-Grow-Automation/GanjOS_Grow_Automation/issues)

---

### 👨‍💻 Code & Dokumentation beitragen

- Forke das passende Repository
- Erstelle einen Branch (`feature/...` oder `bugfix/...`)
- Teste und dokumentiere deine Änderungen
- Eröffne einen Pull Request mit Beschreibung

> 📜 Lies bitte unseren [Verhaltenskodex](./CODE_OF_CONDUCT.md) und die [Mitwirkungsrichtlinien](./CONTRIBUTING.md)

---

### 💬 Community & Austausch

- 👉 Tritt unserem [Community Discord](https://discord.ganjos.io) bei
- 🗣️ Stelle Fragen, teile Setups oder diskutiere Automatisierungen

---

### 💰 Unterstützung durch Spenden & Affiliate-Links

GanjOS ist ein unabhängiges Community-Projekt – dennoch entstehen Kosten für Sensorik, Tests und Dokumentation.

Du kannst uns auf zwei Wegen unterstützen:

1. ☕ **Spende via Ko-Fi**  
   [![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/ganjos)  
   → Ermöglicht neue Hardwaretests & Integration in GanjOS

2. 🛒 **Nutzung von Affiliate-Links & Partnercodes**  
   In unseren [Dokumentationen](./Guides) und auf unserer [Website](https://link.space/@ganjosgrowautomation) findest du viele getestete Produkte mit **Affiliate-Links** und **exklusiven Rabattcodes** für die Community.  
   → Du sparst beim Einkauf – und wir erhalten eine kleine Provision.

> 💡 Jeder Einkauf oder jede Spende hilft dabei, GanjOS weiterzuentwickeln und kompatible Hardware kontinuierlich zu erweitern.

## 👤 Autoren & Entwicklerteam {#autoren--entwicklerteam}

### Offizielles GanjOS Dev Team

- **Marco aka Rocky** – *Gründer, Hauptentwickler & Projektvisionär*  
  [GitHub-Profil](https://github.com/MrcoSchrnr)

> 👥 Die vollständige Liste aller Mitwirkenden findest du hier:  
> [→ GitHub Contributors](https://github.com/Ganjos-Grow-Automation/GanjOS_Grow_Automation/graphs/contributors)

---

## 🏆 Sponsoren {#sponsoren}

Ein herzliches Dankeschön an alle Marken, Partner und Shops, die GanjOS unterstützen – sei es durch Rabatte, Testprodukte oder direkte Förderung.

> 🛒 Eine Übersicht aller aktuellen Sponsoren, Rabattcodes und Affiliate-Partner findest du in unserem  
> [📌 Linkspace-Profil](https://link.space/@ganjosgrowautomation) **und auf** [ganjos.io](https://ganjos.io)

---

## 🙌 Inspiration & Danksagung {#inspiration--danksagung}

Dieses Projekt wurde inspiriert und geprägt von:

- **Eric von Garten Eden** – für den aktiven Support, Austausch und den Glauben ans Projekt
- **HomeGrow Pro**
- **Ben Green**
- **LEDGardener**

Danke an alle, die direkt oder indirekt zum Projekt beigetragen haben!

---

## ☕ Unterstütze GanjOS {#unterstuetze-ganjos}

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/ganjos)

> Mit deiner Unterstützung können wir neue Hardware testen, Dokumentationen schreiben und das Projekt nachhaltig weiterentwickeln.

</details>

---

## 🇬🇧 GanjOS Grow Automation (English) {#ganjos-grow-automation-english}
<details>
<summary>▶️ Click here to learn more about GanjOS</summary>

### 📚 Table of Contents

- [🔧 What is GanjOS?](#what-is-ganjos)
- [🖼️ Preview & Example Setup](#preview--example-setup)
- [🧩 Modules & Components](#modules--components)
- [🚧 Roadmap / Planned Features](#roadmap--planned-features)
- [🛠 Installation & Guides](#installation--guides)
- [🤝 Contributing & Getting Involved](#contributing--getting-involved)
- [📄 License](#license)
- [🧑‍💻 Authors & Community](#authors--community)
- [🌐 Sponsors & Inspirations](#sponsors--inspirations)

## 🔧 What is GanjOS? {#what-is-ganjos}

> ⚠️ **Beta Notice:**  
> GanjOS is currently in **beta phase** – bugs, missing features and changes are to be expected.

**GanjOS** is a community-powered open-source project designed to automate indoor grow environments.  
It aims to provide growers with a **low-cost, data-driven solution** to monitor and optimize their grow conditions – with just a bit of DIY effort.

The system is built on top of [**Home Assistant**](https://www.home-assistant.io/), a powerful open-source home automation platform that allows you to connect, visualize and control all kinds of devices and sensors.

Together with optional add-ons like ESPHome, MQTT or Node-RED, GanjOS enables:
- integration of affordable DIY hardware (like ESP32 microcontrollers)
- continuous **data acquisition** (temp, humidity, CO₂, light, soil)
- **automated control** of lights, climate, ventilation, irrigation
- **documentation & analysis** of your grow over time

If data can be read via Home Assistant – it can be used in GanjOS.

---

### 📱 Follow GanjOS for updates, tips & behind-the-scenes:

- 🌍 Website: [ganjos.io](https://ganjos.io)
- 📲 Instagram: [@ganjos.official](https://www.instagram.com/ganjos.official)  
- 🧪 Lab project: [@ganjos.lab](https://www.instagram.com/ganjos.lab)  
- 🔗 Linkspace hub: [link.space/@ganjosgrowautomation](https://link.space/@ganjosgrowautomation)

## 🖼️ Preview & Example Setup {#preview--example-setup}

GanjOS is built to serve real-world growers – offering a modular, affordable and highly customizable grow automation framework based on Home Assistant.

The screenshots below show a sample dashboard with:
- Real-time data from climate and light sensors
- Stage-based plant area management
- Full VPD integration
- Controllable lighting and ventilation

<details>
<summary>📸 Show screenshots</summary>

![Dashboard 1](https://github.com/user-attachments/assets/ddf5a8eb-5d33-4348-8c36-1cb051d0e90e)
![Dashboard 2](https://github.com/user-attachments/assets/2afe4348-411e-4719-bee6-292ee979a8a4)
![Dashboard 3](https://github.com/user-attachments/assets/a660bdb6-b177-47de-9349-2e881c453ad8)
![Dashboard 4](https://github.com/user-attachments/assets/e07214e1-4957-42bc-aa66-bc48d1135835)

</details>

<details>
<summary>🧰 Example hardware setup for 3 legal plants (Germany)</summary>

**Grow Area:**

- 🌱 **Grow tent**: [`Eden Growbox 110x60x180`](https://www.eden-grow.de/growshop/growboxen/eden-growbox-110-60-80/)
- 💡 **LED lighting**: [`2x SANlight EVO 3-60 incl. dimmer cables`](https://amzn.to/4jlt9Bk) *(affiliate link – supports us at no extra cost)*
- 🌬️ **Oscillating fan**: [`AC Infinity Cloudray S6`](https://amzn.to/43gzCZL) *(affiliate link)*
- 🌫️ **Humidifier**: [`RAM Humidifier 13L`](https://amzn.to/4dx7x3L) *(affiliate link)*
- 🌀 **Exhaust system**: [`Prima Klima EC BLUE 125mm`](https://www.eden-grow.de/growshop/klimatechnik/prima-klima-ec-ventilator-blue-680m3-h-125mm-rj45/)  
  → *Use an active carbon filter if odor needs to be controlled*
- 🧵 **Living soil container**: [`TRUESOIL MSL Bed 100x50x50`](https://truesoil.at/products/living-soil-beet)  
  → *Get a discount using the code “GanjOS” at checkout*

---

**Sensors & Automation:**

> [!IMPORTANT]  
> This example uses basic yet stable sensors. It is focused on environmental monitoring and control – not soil data.  
> Watering is assumed to be handled by passive systems like Blumat.

- 📟 **ESP32 board**: [`FireBeetle 2 ESP32-E`](https://www.dfrobot.com/product-2231.html?tracking=WjyQJqF2zJKV41fDEVNqlL8iIoSaXJXcs510uBhCzQJ0RftedpYAlvGH8TibE7eY) *(affiliate link)*
- 📟 **IO shield**: [`DFRobot IO Expansion Shield`](https://www.dfrobot.com/product-2395.html?tracking=WjyQJqF2zJKV41fDEVNqlL8iIoSaXJXcs510uBhCzQJ0RftedpYAlvGH8TibE7eY) *(affiliate link)*

- 🌡️ **Sensors**:
  - [`SHT31 – Temp/Humidity`](https://www.dfrobot.com/product-2160.html?tracking=WjyQJqF2zJKV41fDEVNqlL8iIoSaXJXcs510uBhCzQJ0RftedpYAlvGH8TibE7eY) *(affiliate link)*
  - [`ENS160 – CO₂ / VOC`](https://www.dfrobot.com/product-2623.html?tracking=WjyQJqF2zJKV41fDEVNqlL8iIoSaXJXcs510uBhCzQJ0RftedpYAlvGH8TibE7eY) *(affiliate link)*

- ⚡ **Smart plugs**: [`4x Shelly Plug S`](https://amzn.to/3FjM8yo) *(affiliate link – for fans, humidifiers etc.)*
- 🎛️ **Smart dimmer**: [`2x Shelly Dimmer 0–10V`](https://amzn.to/3ZtWBxR) *(affiliate link – used for exhaust and light control)*

---

**Other Essentials:**

- 🔌 **Power supply**: [`Rocoren USB-C multi charger`](https://amzn.to/4dxQgaL) *(affiliate link)*
- 📦 **Waterproof housing**: `IP68 case for ESP32` *(placeholder – to be linked)*
- 🔗 **Cabling**: [`Anker USB-C cables`](https://amzn.to/4kmvKw4) *(affiliate link)*

</details>

## 🧩 Modules & Components {#modules--components}

GanjOS is modular by design – you can use only what you need, mix & match, or build upon it with your own logic.

| Module | Description | Repository |
|--------|-------------|------------|
| 🧠 **Home Assistant Integration** | Core logic, ESP32 device registration, entity creation | [`GanjOS_hass_core`](https://github.com/Ganjos-Grow-Automation/GanjOS_hass_core) |
| 🖥️ **Dashboard Templates** | Lovelace YAML dashboards for real-time visualization | [`GanjOS_hass_dashboard`](https://github.com/Ganjos-Grow-Automation/GanjOS_hass_dashboard) |
| 🔁 **Node-RED Flows** | Automation flows for climate, lighting & sensors | [`GanjOS_NodeRED_Flows`](https://github.com/Ganjos-Grow-Automation/GanjOS_NodeRED_Flows) |
| 🎓 **Tutorials & Online Course** | Documentation & premium learning resources *(coming soon)* | [ganjos.io/kurs](https://ganjos.io/kurs) |

## 🚧 Roadmap / Planned Features {#roadmap--planned-features}

GanjOS is evolving to become smarter, more customizable, and more efficient for homegrow automation.  
Here’s what we’re currently planning and working on:

- 🌿 **Crop Steering**: Dynamic adjustment of climate and lighting parameters based on plant development stage
- 🎛️ **Auto Device Dimming**: Percentage-based control for fans, lighting, heaters and humidifiers – driven by VPD and targets
- 🤖 **AI-powered Grow Optimization**: Use of machine learning to predict and automate optimal growing conditions
- 🧠 **Big Data Logging**: Anonymous long-term sensor data storage for pattern recognition and grow insights
- 🧺 **Automated Drying Process**: Guided, controlled drying stages with automatic environmental adjustments
- 🚨 **Advanced Alerting**: Configurable notifications for thresholds, trends, and sensor anomalies (email, app, Discord)

> 💡 Follow our roadmap progress on the  
> [📌 GanjOS HA Integration GitHub Project Board](https://github.com/orgs/Ganjos-Grow-Automation/projects/6)

> 💬 Got a new idea or feature request?  
> 👉 Open a [GitHub Issue in the main repository](https://github.com/Ganjos-Grow-Automation/GanjOS_Grow_Automation/issues)  
> or share your suggestion in the [Community Discord](https://discord.ganjos.io)

## 🛠 Installation & Setup {#installation--setup}

GanjOS is modular – each part can be installed separately, depending on your grow setup.

| Component           | Description                                  | Guide                                         |
|---------------------|----------------------------------------------|----------------------------------------------|
| 🔌 **Integration**  | Main GanjOS Home Assistant custom integration | [→ View Integration Guide](https://github.com/Ganjos-Grow-Automation/GanjOS_hass_core) |
| 🖥️ **Dashboard**    | Lovelace YAML templates for visualization     | [→ Dashboard Repo](https://github.com/Ganjos-Grow-Automation/GanjOS_hass_dashboard) |
| 🔁 **Node-RED**     | Optional automation logic flows               | [→ Node-RED Flows](https://github.com/Ganjos-Grow-Automation/GanjOS_NodeRED_Flows) |

> ℹ️ A basic setup only requires the integration to be installed via HACS and configured through the Home Assistant UI wizard.

---

### 📂 Wiring & Sensor Guides

The [`./Guides`](./Guides) folder contains sample wiring diagrams and ESPHome code for tested sensors and devices used in GanjOS setups.

> ⚠️ **Disclaimer:**  
> All connection instructions and diagrams are provided for educational purposes only.  
> We assume no liability for damage caused by incorrect wiring, misuse, or hardware failures.  
> Always double-check wiring and consult a qualified technician if unsure.

---

### 🎥 Video Tutorials (coming soon)

We’ll soon publish a complete setup guide on our official [YouTube Channel](https://www.youtube.com/@ganjos.official)

We’re also preparing **premium tutorial videos** that explore advanced GanjOS topics, including:

- 📊 How to weight sensor values by plant stage (e.g. VPD vs CO₂ relevance)
- 🖼️ Customizing your dashboard layout and views
- 🔁 Creating your own automations tailored to your setup
- 📈 Interpreting grow data to optimize long-term performance

> 📌 Access to premium tutorials will be available via our [Ko-Fi Page](https://ko-fi.com/ganjos)

## 📄 License {#license}

GanjOS is released under a **dual-license model**:

1. **Private and non-commercial use**  
   → Permitted under the terms of the [MIT License](./LICENSE)

2. **Commercial use** (e.g. grow shops, social clubs, SaaS platforms)  
   → Requires a paid license

> 📩 For commercial licensing, please contact us at [info@ganjos.io](mailto:info@ganjos.io)

---

### ⚠️ Notice on Commercial Use

Unauthorized commercial use of GanjOS is a violation of the license terms.  
We reserve the right to take legal action and claim damages in such cases.

To stay compliant, please contact us for a commercial license:  
[info@ganjos.io](mailto:info@ganjos.io)


## 🤝 Contributing & Supporting {#contributing--supporting}

Whether through code, feedback or support – every contribution helps GanjOS grow. Here’s how you can get involved:

---

### 🐛 Report Bugs & Suggest Features

- Found a bug or have an idea?  
  → Open a [GitHub Issue in the main repository](https://github.com/Ganjos-Grow-Automation/GanjOS_Grow_Automation/issues)

---

### 👨‍💻 Contribute Code or Docs

- Fork the relevant repository
- Create a branch (`feature/...` or `bugfix/...`)
- Test your changes and document them
- Open a Pull Request with a clear summary

> 📜 Please review our [Code of Conduct](./CODE_OF_CONDUCT.md) and [Contributing Guidelines](./CONTRIBUTING.md) before contributing.

---

### 💬 Join the Community

- 👉 Join our [Community Discord](https://discord.ganjos.io)
- 🗣️ Discuss ideas, setups and automations

---

### 💰 Support via Donations & Affiliate Links

GanjOS is fully independent – but hardware testing and documentation comes at a cost.

You can support us in two ways:

1. ☕ **Donate via Ko-Fi**  
   [![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/ganjos)  
   → Helps fund new sensor tests and GanjOS integration

2. 🛒 **Use our Affiliate Links & Partner Codes**  
   Our [docs](./Guides) and [website](https://link.space/@ganjosgrowautomation) include **affiliate links** and **community discount codes** for verified products.  
   → You save money – we earn a small commission.

> 💡 Every donation or purchase helps us maintain GanjOS and expand support for new devices.

## 👤 Authors & Core Team {#authors--core-team}

### Official GanjOS Dev Team

- **Marco aka Rocky** – *Founder, Lead Developer & Project Visionary*  
  [GitHub Profile](https://github.com/MrcoSchrnr)

> 👥 View the full contributor list:  
> [→ GitHub Contributors](https://github.com/Ganjos-Grow-Automation/GanjOS_Grow_Automation/graphs/contributors)

---

## 🏆 Sponsors {#sponsors}

Big thanks to all brands, partners, and shops supporting the GanjOS project – through discounts, product samples or direct collaboration.

> 🛒 You’ll find an up-to-date list of sponsors, discount codes and affiliate partners in our  
> [📌 Linkspace profile](https://link.space/@ganjosgrowautomation) **and on** [ganjos.io](https://ganjos.io)

---

## 🙌 Acknowledgements & Inspiration {#acknowledgements--inspiration}

This project was inspired and shaped by:

- **Eric from Garten Eden** – for his active support, valuable input and belief in the project
- **HomeGrow Pro**
- **Ben Green**
- **LEDGardener**

Thanks to everyone who helped GanjOS grow in any form!

---

## ☕ Support the Project {#support-the-project}

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/ganjos)

> Your donation helps us test new hardware, create detailed guides, and keep the project thriving.

</details>