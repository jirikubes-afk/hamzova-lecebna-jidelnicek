# 🍽️ Jídelníček Hamzova léčebna

[![GitHub Pages](https://img.shields.io/badge/Demo-GitHub%20Pages-blue)](https://YOUR_USERNAME.github.io/hamzova-lecebna-jidelnicek/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Demo aplikace pro zobrazení jídelníčku Hamzovy léčebny z ISP API systému.

## 🌐 Demo

👉 **[Živá ukázka na GitHub Pages](https://YOUR_USERNAME.github.io/hamzova-lecebna-jidelnicek/)**

## ✨ Funkce

- 📅 **Výběr období** - Zobrazení jídelníčku pro libovolné datum
- 🗓️ **Týdenní navigace** - Rychlé přepínání mezi týdny
- 🥗 **Kompletní menu** - Snídaně, obědy, večeře s variantami
- ⚠️ **Alergeny** - Zobrazení alergenů podle vyhlášky
- 📱 **Responsivní design** - Funguje na všech zařízeních
- 🔄 **Automatické načítání** - Aktuální týden při otevření

## 🚀 Rychlý start

### Pro zobrazení demo:
1. Navštivte [GitHub Pages demo](https://YOUR_USERNAME.github.io/hamzova-lecebna-jidelnicek/)
2. Demo používá veřejné CORS proxy pro přístup k API

### Pro lokální spuštění:
```bash
# Naklonujte repository
git clone https://github.com/YOUR_USERNAME/hamzova-lecebna-jidelnicek.git

# Přejděte do složky
cd hamzova-lecebna-jidelnicek

# Otevřete v prohlížeči
open index.html
# nebo spusťte lokální server
python -m http.server 8000
# pak otevřete http://localhost:8000
```

## 📁 Struktura projektu

```
├── index.html                    # Hlavní aplikace (GitHub Pages)
├── jidelnicek-iframe.html        # Verze pro iframe (přímé API volání)
├── jidelnicek-iframe-php.html   # Verze pro iframe (s PHP proxy)
├── jidelnicek-proxy.php         # PHP proxy pro obejití CORS
├── integrace-iframe-priklady.html # Příklady integrace
├── DOKUMENTACE.md               # Kompletní technická dokumentace
├── GITHUB-NAVOD.md             # Návod pro GitHub Pages
└── README.md                   # Tento soubor
```

## 🔧 Technologie

- **Frontend:** Vanilla JavaScript, HTML5, CSS3
- **API:** ISP Catering API
- **CORS řešení:** Veřejné proxy servery (demo) / PHP proxy (produkce)
- **Hosting:** GitHub Pages (demo)

## 🛠️ Konfigurace

### Změna výdejny
V souboru `index.html` najděte a upravte:
```javascript
const VYDEJNY_ID = 1; // Změňte ID podle potřeby
```

### Vlastní styling
Upravte CSS styly přímo v `<style>` sekci v `index.html`.

## ⚠️ Důležité upozornění

### CORS omezení
- **Demo verze** používá veřejné CORS proxy servery (nestabilní, pouze pro testování)
- **Pro produkci** je nutné implementovat vlastní backend nebo proxy server

### Produkční nasazení
Pro produkční použití doporučujeme:
1. **PHP backend** - použijte `jidelnicek-proxy.php` na vlastním serveru
2. **Serverless funkce** - Vercel, Netlify Functions
3. **Vlastní API gateway** - AWS, Azure, Google Cloud

## 📋 API Dokumentace

### Endpoint
```
https://strava.hamzova-lecebna.cz/isp/api/catering/menu/full/{vydejnaId}
```

### Parametry
- `vydejnaId` - ID výdejny (např. 1)
- `beg` - Datum od (formát YYYYMMDD)
- `end` - Datum do (formát YYYYMMDD)

### Příklad volání
```
GET /isp/api/catering/menu/full/1?beg=20250101&end=20250107
```

### Struktura odpovědi
```json
[
  {
    "date": "20250101",
    "meal_type": "snídaně",
    "option": "1",
    "meal": "Název jídla",
    "allergens": [
      {
        "code": "1",
        "name": "Lepek"
      }
    ]
  }
]
```

## 🤝 Přispívání

Příspěvky jsou vítány! Pro větší změny nejprve otevřete issue.

## 📝 Licence

Tento projekt je licencován pod MIT licencí.

## 👥 Autoři

- Vytvořeno pro Hamzovu léčebnu

## 🙏 Poděkování

- Hamzova léčebna za poskytnutí API
- Komunita za CORS proxy servery

## 📞 Kontakt

Pro dotazy ohledně implementace kontaktujte IT oddělení Hamzovy léčebny.

---

⭐ Pokud se vám projekt líbí, dejte mu hvězdičku!
