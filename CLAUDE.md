# CLAUDE.md — Inspektor X

## Projekti ülevaade
Mobiilne visuaalse kontrolli tööriist tehnikutele ja inspektoritele.
Pildista probleem. Lisa häälkommentaar. Genereeri PDF raport.

## Arhitektuur
- **Tüüp:** PWA — Progressive Web App
- **Failid:** index.html + manifest.json + sw.js + ikoonid
- **Andmesalvestus:** IndexedDB (3 tabelit: sess, kirjed, pildid)
- **Backend:** puudub — 100% lokaalne, offline-first
- **PDF:** prindi dialoog (client-side, ei vaja serverit)
- **Keel:** Eesti UI, inglise kood
- **Platvorm:** Android Chrome, iOS Safari
- **GitHub:** https://github.com/Anar-dev-Clau/Inspektor-X

## Andmestruktuur
```
sess      — id, aeg, nimi
kirjed    — id, aeg, sessId, nimi
pildid    — id, aeg, kirjeId, pilt(base64), heli(base64), heliSecs, heliType
```

## Kolmetasandiline struktuur
```
Inspektsioon (sess)
└── Kirje — seadme nimi (nt "Pump 24")
    ├── Pilt 1 — foto + hääl
    ├── Pilt 2 — foto + hääl
    └── Pilt 3 — foto + hääl
```

## Töövoog
1. Uus inspektsioon → sisesta koha nimi
2. Lisa kirje → sisesta seadme nimi
3. Lisa pilt → kaamera → pildista → hääl → salvesta
4. Pärast salvestamist: Jätka / Uus kirje / Lõpeta
5. Lõpeta → Raport → Genereeri PDF → prindi dialoog → Salvesta PDF-ina

## KRIITILISED REEGLID
- ARA muuda IndexedDB skeemi (DB_NAME = 'InspektorX3') ilma migratsioonita
- ARA lisa pilve/network funktsioone — 100% offline
- Hoia kõik ühes HTML failis (v.a. manifest.json ja sw.js)
- Eesti UI tekst, inglise muutujad/kood
- Oranž (--amber: #f0a500) informatiivne tekst, roheline (--accent: #00c2a8) funktsiooninupud

## Lukupunktid

### LUKUPUNKT 1 — Rakendus töötab
**Kuupäev:** 2026-04-17

**Valmis ja testitud:**
- Avakuva sessioonide nimekirjaga + hoiatus üle 10 sessiooni
- Uus inspektsioon — koha nimi
- Lisa kirje — seadme nimi
- Lisa pilt — kaamera (front/back) + häälkommentaar
- Pärast salvestamist: Jätka / Uus kirje / Lõpeta
- Galerii — sessioon → kirje → pildid pisipiltidega
- Detail — pilt suurelt + hääl mängida
- Kustutamine koos kinnitusega (sessioon / kirje / pilt)
- PDF raport — objekt, kuupäev, kirjed, pildid, ajatemplid
- PWA — installitav avakuvale
- Offline — töötab ilma internetita

## Järgmised võimalikud sammud
- Otsing sessioonide nimekirjas
- Tekstikommentaar pildile (vabatahtlik)
- Inspektor Pro — eelseadistatud objektide nimekiri (Variant B)
