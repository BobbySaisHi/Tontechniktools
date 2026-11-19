# Quellen

Übersicht aller Quellen und Annahmen des Tools „Mikrofon im Schallfeld“.
Im Code stehen die Quellen zusätzlich als Kommentar direkt an den Formeln (`index.html`, Block `<script id="physics">`).

## 1 Literatur

| Kürzel | Quelle | Verwendet für |
|---|---|---|
| [BM] | L. L. Beranek, T. J. Mellow: *Acoustics: Sound Fields and Transducers*. Academic Press, 2012 | Kugelwelle einer Punktquelle, Verhältnis Schnelle zu Druck, Phasenversatz, 1/r-Gesetz |
| [DH] | M. Dickreiter, V. Dittel, W. Hoeg, M. Wöhr (Hrsg.): *Handbuch der Tonstudiotechnik*, 8. Auflage. De Gruyter, 2014 | Mikrofone: Druck- und Gradientenempfänger, Richtcharakteristiken, Druckstau, Bündelung, Gradientenfehler, Frei- und Diffusfeldentzerrung, Hallradius |

Die Formeln des Kapselmodells sind bewusst stark vereinfacht. Sie wurden in der Projektvorgabe (`CLAUDE.md`) festgelegt und dort [DH] zugeordnet. Konkrete Seitenzahlen sind bisher nicht geprüft.

## 2 Formeln und Modelle

Konstanten und Größen: c = 343 m/s (Luft, ca. 20 °C), k = 2πf/c, λ = c/f, a = D/2.

| Größe | Formel | Quelle |
|---|---|---|
| Schnelle relativ zu p/ρc (Kugelwelle) | N = 1 − j/(k·r) | [BM] |
| Betrag, Schnelle-Überschuss | \|N\| = √(1 + 1/(kr)²), Pegel 20·log10\|N\| | [BM] |
| Phasenversatz p/v | φ = arctan(1/(kr)), v eilt p nach | [BM] |
| Übergangsfrequenz | k·r = 1 → f = c/(2πr) | [BM] |
| Amplitude über Abstand | p ∝ 1/r, bezogen auf p bei 1 m | [BM] |
| Flächenzuwachs innerhalb λ | ((r + λ)/r)² − 1 | Geometrie der Kugeloberfläche |
| Nahbesprechung, ideale Wandler (Achse) | Kugel H = 1, Acht H = N, Niere H = 0,5 + 0,5·N | [BM], [DH] |
| Druckstau Kugel auf Achse | G0² = (1 + 4(ka)²)/(1 + (ka)²), bis +6 dB | [DH], vereinfacht |
| Bündelungsgrad Kugel | Q = 1 + (ka)² | [DH], vereinfacht |
| Gradientenfehler (Umweg d = D) | S = sin(kd/2)/(kd/2), Nullstelle bei f = c/D, Pegel unten bei −40 dB begrenzt | [DH], vereinfacht |
| Freifeld auf Achse mit Kapsel | Kugel G0, Acht S·N, Niere 0,5·G0 + 0,5·S·N | [DH], vereinfacht |
| Diffusfeld-Leistung | Kugel G0²/Q, Acht S²/3, Niere (0,5·G0/√Q + 0,5·S)²/3 | [DH], vereinfacht |
| Direkt- und Diffusschall, Hallradius | E = (r_H/r)²·\|H_frei\|² + Γ; bei r = r_H sind Direkt- und Diffusanteil gleich | [DH] |
| Kugel freifeldentzerrt | Leistungsfaktor 1/G0² | [DH] |
| Kugel diffusfeldentzerrt | Leistungsfaktor Q/G0² | [DH] |
| Kugel Zwischenstufe | Leistungsfaktor √Q/G0² (halbe Diffusfeldanhebung in dB) | Projektvorgabe (`AUFTRAG-2.md`) |
| Polardiagramm Kugel (vereinfacht) | D(θ) = (1 − B) + B·cos θ, B aus (1 − B)² + B²/3 = 1/Q, Q höchstens 4, Achse mit G0 skaliert | Bündelungsgrad von Charakteristiken erster Ordnung: [DH]; Begrenzung Projektvorgabe |
| Energieanteile in der Saalskizze | direkt ∝ (r_H/r)², diffus = 1 (Kugel, breitbandig) | aus der Definition des Hallradius [DH] |
| Normierung | Pegel relativ zu 1 kHz | Datenblatt-Konvention |

## 3 Daten und Annahmen

Es werden keine Messdaten verwendet. Alle Kurven werden aus den Formeln oben berechnet.
Folgende Werte sind eigene, schematische Annahmen:

- Startwerte und Regelbereiche (Abstand, Frequenz, Hallradius, Kapseldurchmesser): Projektvorgabe (`CLAUDE.md`, `AUFTRAG-2.md`)
- Schnellwahl-Abstände 5 cm, 30 cm, 8 m: typische Werte, Projektvorgabe
- Saalskizze: Maße von Bühne, Bühnenkante (2 m vor der Quelle), Sitzreihen (Abstand 0,9 m) und Kopf (Radius 9 cm) frei gewählt, nicht maßstäblich zu einem realen Saal
- Darstellung der Kreiswelle: Keil ±22°, Ausschnitt 6 λ, Grenzen 0,02 λ bis 5 λ, eine Periode dauert in der Animation 2 s

## 3a Vereinfachte Version (`nahfeld-fernfeld-simplified/`)

Gleiche Formeln wie oben, zusätzlich folgende schematische Annahmen:

- Bändchenmikrofon: ideale Acht (Nahbesprechung, Diffusfeld-Leistung 1/3) mit sanftem Höhenabfall als Tiefpass 2. Ordnung, |H|² = 1/(1 + (f/12 kHz)⁴) – Annahme für die Lehre (typischer weicher Höhenabfall), keine Daten eines bestimmten Modells, kein Kammfilter
- Raumwahl: trocken / normal / hallig entspricht Hallradius 2,5 m / 1 m / 0,5 m (eigene, runde Werte)
- Kapseldurchmesser fest 25 mm
- Bezugspegel 0 dB: gleiches Mikrofon bei 1 kHz ohne Nahbesprechungseffekt (eigene Festlegung)
- Automatischer Zoom der Saalskizze auf den Kopf bei Abstand unter dem halben Hallradius (höchstens 0,8 m): eigene Festlegung

## 4 Software und Gestaltung

- Keine externen Bibliotheken, Schriften oder Dienste. Alles steht in einer Datei `index.html` (HTML, CSS, JavaScript).
- Grafik mit dem HTML-Canvas des Browsers.
- Schrift: Arial bzw. die Systemschrift des Browsers.
- Grafischer Stil (Farben, Schrift, Kästen, Wertanzeigen) übernommen aus `reference/index.html`. Funktion und Code der Referenz wurden nicht übernommen.
- Farbskala der Abstandskarte: eigene divergierende Skala von Blau (#0066cc, Akzentfarbe der Referenz) über Weiß zu Orange.
- Der Code wurde mit KI-Unterstützung (Claude Code, Anthropic) geschrieben. Es wurde kein fremder geschützter Code übernommen.

## 5 Prüfung

Die Plausibilitätstests in `runPhysicsTests()` (Browser-Konsole) prüfen die Formeln gegen die Sollwerte aus `CLAUDE.md`, Abschnitt „Plausibilitätsprüfung“.
