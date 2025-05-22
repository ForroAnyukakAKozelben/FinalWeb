# 🌍 Utazásom – Egyszerű HTML weboldal

Ez egy statikus weboldal, amely három egyszerű, egységes stílusú HTML-oldalból áll: **kezdőlap**, **úticélok** és **statisztikai galéria**.

A célja: egy letisztult, tartalmas és reszponzív élmény megvalósítása JavaScript nélkül (vagy csak minimális, hasznos JavaScripttel).

---

## 🔗 Oldalak

- **index.html** – Kezdőlap, bevezető szövegekkel, galériával és ajánlásokkal.
- **destinations.html** – Kedvenc úticélok táblázatban és képekben, kereső funkcióval.
- **gallery.html** – Statisztikai adatok táblázatban és grafikonon, képekkel.

---

## 📦 Mappastruktúra

projekt/
│
├── images/
│ ├── beach.jpg
│ ├── mountain.jpg
│ └── ...
│
├── index.html
├── destinations.html
├── gallery.html
└── README.md

yaml
Másolás
Szerkesztés

---

## 🖼️ Képernyőkép

> *(Tölts fel ide egy screenshotot a weboldalról)*  
> Pl.: ![Utazásom kezdőlap](images/screenshot.png)

---

## 💡 Példák és magyarázatok

### 📌 Lábléc a képernyő aljára (még rövid tartalom esetén is)

Az alábbi CSS biztosítja, hogy a lábléc mindig az oldal alján maradjon:

```css
body {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.container {
  flex: 1;
}
Ez azt jelenti, hogy a .container kitölti a helyet a <header> és a <footer> között.

🔎 Kereső funkció a táblázathoz
A destinations.html oldal tartalmaz egy valós idejű keresőt JavaScript segítségével:

html
Másolás
Szerkesztés
<input type="text" id="searchInput" placeholder="Szűrés ország vagy város alapján...">
js
Másolás
Szerkesztés
document.getElementById("searchInput").addEventListener("input", function () {
  const filter = this.value.toLowerCase();
  const rows = document.querySelectorAll("#destinationTable tbody tr");

  rows.forEach(row => {
    const city = row.cells[1].textContent.toLowerCase();
    const country = row.cells[2].textContent.toLowerCase();
    row.style.display = (city.includes(filter) || country.includes(filter)) ? "" : "none";
  });
});
📅 Automatikus év megjelenítés a láblécben
Az index.html és gallery.html fájlban:

html
Másolás
Szerkesztés
<p id="yearText">Készítette: Forró Dominik</p>
js
Másolás
Szerkesztés
const yearText = document.getElementById("yearText");
const currentYear = new Date().getFullYear();
yearText.innerHTML = `Készítette: Forró Dominik &copy; ${currentYear}`;
✅ Technológiák
HTML5

CSS3 (reszponzív flexbox-alapú elrendezés)

Minimális, célorientált JavaScript

Chart.js (csak a gallery.html oldalon, CDN-en keresztül)

📚 Források
Chart.js

Lonely Planet

UNESCO World Heritage