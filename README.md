# Overvågningssystem for eksisterende anlæg

## 🧭 Projektbeskrivelse
En kunde ønsker at etablere overvågning på et eksisterende system, der ikke selv kan logge sine data.  
Kunden besidder domæneviden til at optimere systemet, men mangler indsigt i systemets opførsel over tid.

### 🎯 Formål
Projektets mål er at:
1. **Opsamle data** fra det eksisterende system  
2. **Sende data** til en backend (cloud eller self-hosted)  
3. **Gemme data** i backend-databasen  
4. **Præsentere data** for kunden via API eller frontend  

Dette skaber grundlag for, at kunden kan analysere systemets performance og identificere optimeringsmuligheder.

---

## ⚙️ Systemoversigt
Projektet består af flere komponenter, som arbejder sammen i et containeriseret miljø via **Docker Compose**.

### 🧩 Komponenter
- **ESP_Modbus_Slave**  
  Testkode, der simulerer et Modbus-slave-system, som sender data videre.
  
- **paho-pub / paho-sub**  
  MQTT-komponenter baseret på Sparkplug B-protokollen, som håndterer publicering og modtagelse af data.

- **mainapi.py**  
  Hoved-API’en, der modtager og videresender data til backend samt tilbyder endpoints til visning og forespørgsler.

- **Backend (Database / API / Frontend)**  
  Gemmer den opsamlede data og stiller den til rådighed for kunden via API og evt. visualisering.

- **Dockerfile & docker-compose.yml**  
  Bruges til at bygge og køre hele miljøet i containere.

---

## 🗂️ Projektstruktur
```plaintext
projektmappe/
├── docker-compose.yml
├── Dockerfile
├── mainapi.py
├── paho-pub/
│   └── ...
├── paho-sub/
│   └── ...
├── ESP_modbus_slave/
│   └── testkode/
├── requirements.txt
├── CMakeLists.txt
└── README.md
