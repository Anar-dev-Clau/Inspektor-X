# Inspektor X

Mobiilne visuaalse kontrolli tööriist liikuvatele tehnikutele ja inspektoritele.

Pildista probleem. Lisa häälkommentaar. Genereeri PDF raport. Saada edasi.

---

## Mis see on

Inspektor X on PWA (Progressive Web App) mis töötab telefoni avakuvalt nagu päris rakendus — ilma App Store'i, ilma pilve, ilma pideva internetiühenduseta.

Tehnik liigub objektil, dokumenteerib leitud probleemid piltide ja häälkommentaaridena. Töö lõppedes genereeritakse ühe nupuvajutusega PDF raport mis on kohe saadetav juhtkonnale, kliendile või arhiivi.

---

## Peamised omadused

- **Pildistamine + häälkommentaar** — ühe puudutusega, maksimaalne kiirus
- **Offline-first** — töötab täielikult ilma internetita pärast esmast laadimist
- **PDF raport** — genereeritakse seadmes, ei lähe pilve
- **Sessioonid** — üks inspektsioon = üks sessioon, mitu kirjet sees
- **PWA** — installitakse avakuvale, töötab nagu natiivne äpp
- **Privaatsus** — andmed ei lahku seadmest ilma kasutaja tegevuseta

---

## Tehniline ülevaade

| | |
|---|---|
| Tüüp | PWA — Progressive Web App |
| Arhitektuur | Üks HTML fail + manifest + service worker |
| Andmesalvestus | IndexedDB (lokaalne, seadmes) |
| Backend | Puudub — 100% client-side |
| PDF genereerimine | Client-side (seadmes) |
| Platvorm | Android Chrome, iOS Safari |

---

## Kasutamine

1. Ava link telefoni brauseris
2. Vali "Lisa avakuvale" / "Add to Home Screen"
3. Ava rakendus avakuvalt
4. Alusta uut inspektsiooni → pildista → lisa hääl → korda
5. Inspektsioon lõpetatud → "Loo raport" → PDF → jaga

---

## Staatus

🚧 **Arenduses**

---

## Seotud projektid

[Hetk Hetkes](https://github.com/Anar-dev-Clau/hetk-hetkes) — sama tuumik, isiklik ideede salvestaja ilma ekspordita
