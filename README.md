# plaintext-modul-demo

Die Demo-Tabelle von [plaintext-demo](https://github.com/Plaintext-Gmbh/plaintext-demo) als eigenes
Modul: jede Variante der konfigurierbaren Tabelle `pt:tableSettings` von plaintext-root, mit Menü,
Dashboard-Kachel, globaler Suche und Texten in vier Sprachen. Tabelle `demo_product` (Flyway-Migration
im Modul).

Offen, MPL-2.0. Herausgelöst aus plaintext-demo (Karte 2412, siehe `QUELLSTAND.txt`).

## Einbau in eine Plaintext-App

```xml
<dependency>
    <groupId>ch.plaintext</groupId>
    <artifactId>plaintext-modul-demo</artifactId>
    <version>1.0.0</version>
</dependency>
```

Bezug aus Reposilite `https://maven.plaintext.ch/releases`, root ≥ 3.58.0. Beispieldaten füllt die
Anwendung selbst (in plaintext-demo: `plaintext-demo-daten`).

## Entwicklung

```bash
mvn verify   # liest root-v2 aus Reposilite (maven.plaintext.ch, nur im LAN), ohne Anmeldung
```

## Release

Git-Tag `X.Y.Z` pushen: `.woodpecker/release.yml` ruft `ci/release.sh` und legt das Jar in
Reposilite ab (Secret `maven_nas_token`, nur Ereignis tag). Versionen sind unveränderlich;
`ci/release.sh --trocken` prüft vorher, ob die Version frei ist.
