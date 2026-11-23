# Home Assistant Dashboards: Wall und Pixel

Zwei Lovelace-Dashboards für Home Assistant (getestet mit 2026.11):

- **`dashboards/wall.yaml`**: für ein quadratisches Wandpanel (Shelly Wall Display, 480 × 480 px, Android-7-WebView), im Kiosk-Modus ohne Kopfleiste.
- **`dashboards/pixel.yaml`**: Hochformat-Variante fürs Handy, ohne Kiosk-Modus, mit ein paar Extras (24-h-Energiegraph, Klima-Graph, Regenradar).

Beide Dashboards haben dieselben 11 Ansichten: Start, Energie (Energiefluss mit PV, Netz, Akku und Verbrauchern), Klima, Licht, Rollläden, Wallbox, Saugroboter, Mähroboter, Türklingel, Musik/Radio und Wetter.

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
- Die Energie-, Wärmepumpen-, Backofen- und Kochfeld-Werte stammen teils aus eigenen Template-Sensoren (Schätzungen). Diese sind nicht Teil dieses Repos.
- Die Radio-Kacheln nutzen die Skripte `script.radio_starten`, `script.radio_stopp` und `script.radio_lautstaerke` sowie `input_select.radio_ziel`. Auch diese sind nicht enthalten.
