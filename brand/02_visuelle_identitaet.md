# 02 – Visuelle Identität

Stand 06.09.2026 · Entwurf v1

## 1. Gestaltungsprinzip

Das Schweizer Gesundheitswesen sieht überwiegend gleich aus: helles
Pastellblau oder -grün, runde Sans-Serif, lächelnde Menschen im Gegenlicht,
ein stilisiertes Herz oder eine Hand. Wer so aussieht, ist in Sekunde eins
austauschbar.

**Gegenposition: die Marke sieht aus wie ein Instrument, nicht wie eine
Broschüre.** Dunkler Grund, Messing, harte Linien, präzise Zahlen,
zurückhaltende Serifen. Der Referenzraum ist die Intensivstation bei Nacht
und das Archiv — nicht die Wellness-Abteilung.

## 2. Die Bildmarke — Der Ring

Eine Scheibe, gekreuzt von einem geneigten Ring.

- Die **Scheibe** ist der Mensch, der Kern, der Fall.
- Der **Ring** ist das Kompetenzkontinuum: geschlossen, ohne Anfang und
  Ende. Aus der Achse Psychiatrie ↔ Intensivpflege wird ein Kreis.
- Die **Neigung** ist die Achse selbst, ca. 22°.
- Die Form ist saturnisch, ohne Saturn zu sagen.

**Warum sie in Sekunden trägt:** Auf 16 px bleibt ein Punkt mit einer
Linie hindurch — reduzierbar bis zum Favicon, in keiner Schweizer
Gesundheitsmarke besetzt, aus jeder Distanz und in jeder Grösse identisch
lesbar. Sie funktioniert einfarbig, geprägt, gestickt und graviert.

### Konstruktion

| Element | Wert |
|---|---|
| Scheibendurchmesser | 42 Einheiten Radius auf 200er Raster |
| Ring, grosse Halbachse | 78 |
| Ring, kleine Halbachse | 26 |
| Neigung | −22° |
| Strichstärke Ring | 7 (1/6 des Scheibenradius) |
| Schutzraum | 0.5 × Scheibendurchmesser rundum |
| Mindestgrösse digital | 16 px Höhe |
| Mindestgrösse Druck | 6 mm Höhe |

## 3. Das Siegel — Sekundärzeichen

Das SATOR-Quadrat als 5×5-Raster:

```
S A T O R
A R E P O
T E N E T
O P E R A
R O T A S
```

Verwendung **ausschliesslich** auf Zertifikaten, Kursabschlüssen,
Fachpublikationen und Premium-Drucksachen. Es signalisiert genau das, was
die saturnische Rolle verspricht: bewahrtes, geprüftes Wissen.

Nie auf Werbemitteln, nie animiert, nie als App-Icon. Sonst kippt es ins
Esoterische.

## 4. Farbe

Kein cremefarbener Editorial-Look, kein Pastellblau. Der Grund ist
Instrument, nicht Papier.

### Dunkel (Primärwelt)

| Name | Hex | Rolle |
|---|---|---|
| Blei | `#191C21` | Grundfläche |
| Schiefer | `#23272E` | erhobene Fläche, Karten |
| Kalklicht | `#E6E3DC` | Text auf dunklem Grund |
| Nebel | `#8D949E` | Sekundärtext, Beschriftung |
| **Messing** | `#B08D3F` | Akzent, der Ring, genau eine Sache pro Fläche |
| Vigilanz | `#4FA8A0` | ausschliesslich funktional: Daten, Skalen, Zustände |

### Hell (Sekundärwelt)

| Name | Hex | Rolle |
|---|---|---|
| Protokoll | `#E9EAEC` | Grundfläche, kühl, nicht creme |
| Blatt | `#F5F6F7` | erhobene Fläche |
| Blei | `#191C21` | Text |
| Grafit | `#5C636D` | Sekundärtext |
| Messing dunkel | `#8A6D24` | Akzent, kontrastfest auf hellem Grund |
| Vigilanz dunkel | `#2E6F6B` | funktional |

**Regeln**
- Messing ist Akzent, nie Fläche. Höchstens ein Messing-Element pro
  Blickfeld.
- Vigilanz ist nie dekorativ. Es markiert ausschliesslich Daten und
  Zustände.
- Kontrastprüfung WCAG AA für alle Text-/Grundkombinationen ist ein
  eigenes Arbeitspaket (AP-09), keine Annahme.

## 5. Typografie

| Rolle | Schrift | Lizenz | Ausbaupfad |
|---|---|---|---|
| Wortmarke, Titel | **Spectral** | SIL OFL, frei | Lyon Text |
| Fliesstext, Oberfläche | **IBM Plex Sans** | SIL OFL, frei | Suisse Int'l (Swiss Typefaces) |
| Daten, Skalen, Code | **IBM Plex Mono** | SIL OFL, frei | — |

Begründung: Spectral ist eine für den Bildschirm entworfene, nüchterne
Serif ohne dekorative Geste — Dauer ohne Nostalgie. IBM Plex ist
institutionell, technisch und in der Schweizer Gesundheitslandschaft
unverbraucht. Beide sind frei lizenziert; das Jahr-1-Budget geht in
Rechtsprüfung, nicht in Schriftlizenzen.

**Wortmarke:** SATOR in Spectral, Versalien, Laufweite +0.18 em.
Die weite Laufweite macht aus fünf Buchstaben eine Fläche und trennt sie
optisch von SATO.

Typoskala 1.250: 12 / 15 / 19 / 23 / 29 / 37 / 46 px.
Zeilenlänge Fliesstext maximal 65 Zeichen.
Zahlen in Tabellen immer `tabular-nums`.

## 6. Die Signaturgrafik — Die Kontinuum-Skala

Das einzige bildliche Element, das die Marke wiederholt einsetzt: eine
horizontale Skala nach dem Vorbild klinischer Bewertungsskalen (RASS von
−5 bis +4, GCS von 3 bis 15). Sie trägt an ihren Enden Psychiatrie und
Intensivpflege, dazwischen die Pflege.

Sie ist gleichzeitig Diagramm und Markenzeichen: Kurslandkarte,
Kompetenzraster, Beratungsprodukt, Illustrationsprinzip. Wo die Marke
etwas erklärt, erklärt sie es auf dieser Skala.

## 7. Bildsprache

- Keine Stockfotografie. Keine lächelnden Modelle im Gegenlicht.
- Wenn Menschen, dann Hände bei der Arbeit, ohne Gesicht, ohne Pose.
- Objekte statt Situationen: Geräte, Kurven, Formulare, Material.
- Schwarzweiss oder stark entsättigt, ein einziger Messing-Akzent.
- Keine Klientendaten, keine erkennbaren Patienten, nie.

## 8. Anwendungen — Reihenfolge des Aufbaus

1. Wortmarke + Ring (Logopaket, SVG/PNG/EPS, hell und dunkel, einfarbig)
2. Favicon und Social-Avatar (Ring allein)
3. Präsentationsvorlage (Beratung, INSTITUT)
4. Briefschaft, Rechnung, Offerte
5. Website
6. Kurszertifikat mit Siegel
7. LinkedIn- und Fachartikel-Vorlagen
