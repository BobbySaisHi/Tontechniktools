# Mikrofon im Schallfeld – einfach

Vereinfachte, parallele Version des Tools für Einsteigerinnen und Einsteiger.
Sie zeigt nur, wie sich der Klang eines Mikrofons mit dem Abstand zur Quelle verändert –
ohne Reiter, ohne Formeln, mit wenigen Bedienelementen.

## Inhalt

- Abstandsregler (1 cm bis 10 m) mit Schnellwahl und Raumwahl (trocken / normal / hallig)
- Saalskizze, die je nach Abstand und Hallradius automatisch auf den Kopf zoomt
- Frequenzgang für Kugel (freifeld- und diffusfeldentzerrt), Niere und Bändchen (Acht)

## Benutzung

`index.html` im Browser öffnen. Die ausführliche Version liegt eine Ebene höher (`../index.html`).

## Hinweis zum Code

Die Physik (`<script id="physics">`) ist eine Kopie aus `../index.html`. Änderungen an der Physik
müssen in beiden Dateien nachgezogen werden. Die Mikrofonmodelle dieser Version stehen in
`<script id="simple-physics">`. Tests in der Browser-Konsole: `runPhysicsTests()` und `runSimpleTests()`.

Quellen: siehe [../QUELLEN.md](../QUELLEN.md). Änderungen: siehe [CHANGELOG.md](CHANGELOG.md).
