# Changelog – Mikrofon im Schallfeld – einfach

## 0.1.0 – Erste vereinfachte Version

- Eigene Seite im Unterordner, parallel zur ausführlichen Version, mit Link „Zur ausführlichen Version“
- Keine Reiter; ein Abstandsregler 1 cm bis 10 m, Schnellwahl (Gesang 5 cm, Instrument 30 cm,
  Hallradius, Raummikrofon 8 m) und Raumwahl trocken / normal / hallig (Hallradius 2,5 m / 1 m / 0,5 m)
- Saalskizze mit automatischem, weichem Zoom auf den Kopf, wenn das Mikrofon deutlich innerhalb
  des Hallradius steht (Abstand unter dem halben Hallradius, höchstens 0,8 m); bei
  `prefers-reduced-motion` ohne Animation
- Frequenzgang mit dB für Kugel freifeldentzerrt, Kugel diffusfeldentzerrt,
  Niere und Bändchen (Acht mit sanftem Höhenabfall, kein Kammfilter); Kurven ein- und ausblendbar;
  Bereiche Bässe / Mitten / Höhen markiert; Wertanzeige unter dem Mauszeiger
- Bezug 0 dB = gleiches Mikrofon bei 1 kHz ohne Nahbesprechungseffekt. So bleiben die Höhen nah an der
  Quelle auf ihrem echten Pegel (eine reine 1-kHz-Normierung ließe sie scheinbar abfallen, weil der
  Nahbesprechungseffekt bei kleinen Abständen auch 1 kHz noch anhebt)
- Kapseldurchmesser fest (25 mm), kein Frequenzregler
- Kurzer, ausklappbarer Erklärtext; DE/EN; Vollbild
- Konsolen-Tests: alle Tests der ausführlichen Version plus 9 Tests der vereinfachten Version
