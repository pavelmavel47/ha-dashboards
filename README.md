# Home Assistant Dashboards: Wall und Pixel

Zwei Lovelace-Dashboards für Home Assistant (getestet mit 2026.11):

- **`dashboards/wall.yaml`**: für ein quadratisches Wandpanel (Shelly Wall Display, 480 × 480 px, Android-7-WebView), im Kiosk-Modus ohne Kopfleiste.
- **`dashboards/pixel.yaml`**: Hochformat-Variante fürs Handy, ohne Kiosk-Modus, mit ein paar Extras (24-h-Energiegraph, Klima-Graph, Regenradar).

Beide Dashboards haben dieselben 11 Ansichten: Start, Energie (Energiefluss mit PV, Netz, Akku und Verbrauchern), Klima, Licht, Rollläden, Wallbox, Saugroboter, Mähroboter, Türklingel, Musik/Radio und Wetter.

## Screenshots

### Wall (Wandpanel 480 × 480)

| | | |
|---|---|---|
| ![Start](screenshots/wall_start.png)<br>Start | ![Energie](screenshots/wall_energie.png)<br>Energie | ![Klima](screenshots/wall_klima.png)<br>Klima |
| ![Licht](screenshots/wall_licht.png)<br>Licht | ![Rollladen](screenshots/wall_rollladen.png)<br>Rollladen | ![Wallbox](screenshots/wall_wallbox.png)<br>Wallbox |
| ![Roboter](screenshots/wall_roboter.png)<br>Saugroboter | ![Mäher](screenshots/wall_maeher.png)<br>Mähroboter | ![Ring](screenshots/wall_ring.png)<br>Türklingel |
| ![Musik](screenshots/wall_musik.png)<br>Musik | ![Wetter](screenshots/wall_wetter.png)<br>Wetter | |

### Pixel (Handy)

| | | | |
|---|---|---|---|
| ![Start](screenshots/pixel_start.png)<br>Start | ![Energie](screenshots/pixel_energie.png)<br>Energie | ![Klima](screenshots/pixel_klima.png)<br>Klima | ![Licht](screenshots/pixel_licht.png)<br>Licht |
| ![Rollladen](screenshots/pixel_rollladen.png)<br>Rollladen | ![Wallbox](screenshots/pixel_wallbox.png)<br>Wallbox | ![Roboter](screenshots/pixel_roboter.png)<br>Saugroboter | ![Mäher](screenshots/pixel_maeher.png)<br>Mähroboter |
| ![Ring](screenshots/pixel_ring.png)<br>Türklingel | ![Musik](screenshots/pixel_musik.png)<br>Musik | ![Wetter](screenshots/pixel_wetter.png)<br>Wetter | |

Die Screenshots sind bereinigt: Namen ersetzt, Kamerabild, Saugroboter-Karte und Standortmarkierung unkenntlich gemacht, Ortsname durch „Musterstadt“ ersetzt.

## Inhalt

| Datei | Inhalt |
|---|---|
| [`dashboards/wall.yaml`](dashboards/wall.yaml) | Dashboard fürs Wandpanel |
| [`dashboards/pixel.yaml`](dashboards/pixel.yaml) | Dashboard fürs Handy |
| [`docs/ANSICHTEN.md`](docs/ANSICHTEN.md) | Beschreibung jeder Ansicht mit allen verwendeten Entitäten und Aktionen |
| [`packages/dashboard_helpers.yaml`](packages/dashboard_helpers.yaml) | HA-Paket mit allen Helfern, Skripten, Template-Sensoren und Automationen, auf die die Dashboards zugreifen |

## Benötigte Frontend-Erweiterungen

Installierbar über den Marketplace bzw. HACS:

| Erweiterung | Wofür |
|---|---|
| [button-card](https://github.com/custom-cards/button-card) | fast alle Kacheln (JS-Templates) |
| [layout-card](https://github.com/thomasloven/lovelace-layout-card) | `custom:grid-layout` für das Raster |
| [card-mod](https://github.com/thomasloven/lovelace-card-mod) | Styling |
| [kiosk-mode](https://github.com/NemesisRE/kiosk-mode) | Kopfleiste/Seitenleiste auf dem Wandpanel ausblenden |
| [swipe-navigation](https://github.com/zanna-37/hass-swipe-navigation) | Wischen zwischen den Ansichten |
| [apexcharts-card](https://github.com/RomRider/apexcharts-card) | Klima-Graph (Pixel) |
| [mini-graph-card](https://github.com/kalkih/mini-graph-card) | Verlaufsgraph |
| [weather-radar-card](https://github.com/Makin-Things/weather-radar-card) | Regenradar |

## Verwendung

1. In Home Assistant ein neues Dashboard anlegen.
2. Oben rechts ⋮ → *Dashboard bearbeiten* → ⋮ → *Raw-Konfigurationseditor*.
3. Inhalt von `wall.yaml` bzw. `pixel.yaml` einfügen und speichern.
4. Entitäts-IDs an die eigene Installation anpassen. Die Dashboards verweisen auf konkrete Geräte, z. B. Sungrow-Wechselrichter und -Wallbox, EcoFlow Stream, Viessmann-Wärmepumpe, Roborock, Worx Landroid, Ring und Alexa Media Player.

## Hinweise

- Persönliche Kennungen wurden ersetzt: Personen heißen `person.person_1` und `person.person_2`, der Mähroboter `…maehroboter…`. Passwörter, Tokens oder Adressen sind nicht enthalten.
- Die Energie-, Wärmepumpen-, Backofen- und Kochfeld-Werte stammen teils aus eigenen Template-Sensoren (Schätzungen, auf ein bestimmtes Haus kalibriert). Sie stehen samt Radio-Skripten, Garagentor-Skript und den Automationen für Müll-Hinweis und Termine in `packages/dashboard_helpers.yaml`.
- Wechselrichter- und Wallbox-Entitäten kommen aus der Sungrow-Modbus-Integration von [mkaiser](https://github.com/mkaiser/Sungrow-SHx-Inverter-Modbus-Home-Assistant); die ist nicht enthalten.
