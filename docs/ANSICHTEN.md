# Ansichten und Entitäten

Beide Dashboards haben dieselben Ansichten in derselben Reihenfolge. Navigiert wird über die Symbolleiste unten bzw. per Wischen (swipe-navigation).
Die Wall-Variante ist für 480 × 480 px gebaut, die Pixel-Variante fürs Handy-Hochformat.

## Start (`/start`)

Übersicht: Uhrzeit/Datum, Wetter, Müll-Hinweis und Termine des Tages, PV- und Bezugswerte des Tages, laufende Geräte (Saugroboter, Mäher, Waschmaschine ...), Schnellaktionen „Rollladen auf/zu“, „Gute Nacht“ (alles aus) und Wohnlicht. Pixel zusätzlich: Anwesenheit, Warmwasser, Wallbox und Garagentor.

**Aktionen:** `cover.open_cover`, `cover.close_cover`, `homeassistant.turn_off`, `light.turn_on`, `script.turn_on`

<details><summary>Verwendete Entitäten (39 + 5 nur Pixel)</summary>

- `binary_sensor.cu401b_s_kompressor`
- `binary_sensor.cu401b_s_warmwasser_aufladen`
- `binary_sensor.eingangstur_contact`
- `climate.shellywalldisplay_000822781986`
- `cover.rolladen`
- `input_text.muell_hinweis`
- `input_text.termine_heute`
- `lawn_mower.maehroboter`
- `light.ecklampe`
- `light.esstisch`
- `light.fensterlicht_esszimmer`
- `light.fensterlicht_kuche`
- `light.shellywall_browsermod_screen`
- `light.wohnzimmer_gesamt`
- `light.wohnzimmerfernseher_ambilight`
- `light.wohnzimmerlicht`
- `sensor.0xa4c1385290f6bf6b_power`
- `sensor.backofen_aktuelle_garraumtemperatur`
- `sensor.backofen_operation_state`
- `sensor.charging_power`
- `sensor.cu401b_s_aussentemperatur`
- `sensor.daily_direct_energy_consumption`
- `sensor.daily_imported_energy`
- `sensor.daily_pv_generation`
- `sensor.ecoflow_stream_batterie`
- `sensor.ecoflow_stream_batterieleistung`
- `sensor.energy_production_tomorrow_3`
- `sensor.energy_production_tomorrow_4`
- `sensor.kuhlschrank_leistung`
- `sensor.load_power`
- `sensor.meter_active_power`
- `sensor.poolpumpe_leistung`
- `sensor.total_dc_power`
- `sensor.waschmaschine_power`
- `switch.ecklampe`
- `switch.shellyplug_s_80646f81030c`
- `switch.tannenbaum`
- `vacuum.roborock_qv_35s`
- `weather.forecast_home`

Nur Pixel:

- `person.person_1`
- `person.person_2`
- `script.garagentor_ausloesen`
- `sensor.charging_status`
- `sensor.cu401b_s_ww_speichertemperatur`

</details>

## Energie (`/energie`)

Energiefluss (eigene button-card mit SVG): PV, Netz, Hausakku, Haus und bis zu 6 Verbraucher-Kreise (Wallbox, Wärmepumpe mit Phase Heizen/Warmwasser, Backofen, Kochfeld, Spülmaschine, Kühlschrank ...), Phasen L1–L3, Eigenverbrauch und Autarkie. Pixel zusätzlich: PV-Prognose morgen, Einspeisung und 24-h-Leistungsgraph.

<details><summary>Verwendete Entitäten (21 + 4 nur Pixel)</summary>

- `binary_sensor.cu401b_s_kompressor`
- `binary_sensor.cu401b_s_warmwasser_aufladen`
- `sensor.0xa4c1385290f6bf6b_power`
- `sensor.backofen_leistung_geschatzt`
- `sensor.charging_power`
- `sensor.cu401b_s_kompressorphase`
- `sensor.daily_direct_energy_consumption`
- `sensor.daily_exported_energy_from_pv`
- `sensor.daily_imported_energy`
- `sensor.daily_pv_generation`
- `sensor.ecoflow_stream_batterie`
- `sensor.ecoflow_stream_batterieleistung`
- `sensor.kochfeld_leistung_geschatzt`
- `sensor.kuhlschrank_leistung`
- `sensor.load_power`
- `sensor.meter_active_power`
- `sensor.meter_phase_`
- `sensor.poolpumpe_leistung`
- `sensor.total_dc_power`
- `sensor.warmepumpe_leistung_geschatzt`
- `sensor.waschmaschine_power`

Nur Pixel:

- `sensor.daily_exported_energy`
- `sensor.energy_production_tomorrow_3`
- `sensor.energy_production_tomorrow_4`
- `sensor.import_power`

</details>

## Klima (`/klima`)

Außentemperatur, Warmwasser (Speichertemperatur und Solltemperatur) und Wärmepumpe (Viessmann: Kompressor, Leistungszahl), Raumthermostat des Wandpanels mit Solltemperatur-Bedienung, Bad über einen BTHome-Sensor (Temperatur, Luftfeuchte). Pixel zusätzlich: Klima-Graph (apexcharts).

**Aktionen:** `climate.set_temperature`

<details><summary>Verwendete Entitäten (9)</summary>

- `binary_sensor.cu401b_s_kompressor`
- `climate.shellywalldisplay_000822781986`
- `number.cu401b_s_ww_temperatur`
- `sensor.bthome_sensor_85d4_luftfeuchtigkeit`
- `sensor.bthome_sensor_85d4_temperatur`
- `sensor.cu401b_s_aussentemperatur`
- `sensor.cu401b_s_leistungszahl`
- `sensor.cu401b_s_ww_speichertemperatur`
- `water_heater.cu401b_s_warmwasser`

</details>

## Licht (`/licht`)

Alle Lampen und Lampen-Steckdosen als Kacheln zum Schalten, inklusive Ambilight des Fernsehers.

<details><summary>Verwendete Entitäten (9)</summary>

- `light.ecklampe`
- `light.esstisch`
- `light.fensterlicht_esszimmer`
- `light.fensterlicht_kuche`
- `light.wohnzimmerfernseher_ambilight`
- `light.wohnzimmerlicht`
- `switch.ecklampe`
- `switch.shellyplug_s_80646f81030c`
- `switch.tannenbaum`

</details>

## Rollladen (`/rollladen`)

Garagentor (Impuls-Skript) und alle Rollläden einzeln sowie „Alle“, jeweils auf/stopp/zu.

**Aktionen:** `script.turn_on`

<details><summary>Verwendete Entitäten (11)</summary>

- `cover.rolladen`
- `cover.rolladen_esszimmer`
- `cover.rolladen_kinderzimmer`
- `cover.rolladen_kuche`
- `cover.rolladen_schlafzimmer`
- `cover.rolladen_strasse`
- `cover.rolladen_terasse`
- `cover.rolladen_wc_eg`
- `cover.rolladen_wickelzimmer`
- `cover.rolladen_wohnzimmer`
- `script.garagentor_ausloesen`

</details>

## Wallbox (`/wallbox`)

Sungrow-Wallbox: Lademodus (Schnell, Überschuss, Menge, Zeitplan), Laden starten/stoppen, Phasenumschaltung, Netzstrom im Überschussmodus zulassen, Ladestrom, Status und Leistung.

**Aktionen:** `input_select.select_option`, `input_button.press`

<details><summary>Verwendete Entitäten (13)</summary>

- `input_boolean.set_ac_wb_surplus_power_from_grid`
- `input_button.set_ac_wb_start_charging`
- `input_button.set_ac_wb_stop_charging`
- `input_number.set_wb1_output_current`
- `input_select.set_ac_wb_charging_mode`
- `input_select.set_wb_phase_switch`
- `sensor.charged_range`
- `sensor.charging_duration`
- `sensor.charging_energy`
- `sensor.charging_power`
- `sensor.charging_status`
- `sensor.maximum_charging_power`
- `sensor.output_current_setting`

</details>

## Roboter (`/roboter`)

Roborock-Saugroboter: Status, Zurück zur Station, Raumreinigung (Küche, Flur, HWR, Bad, Wohnen, Essen), „Nach dem Essen“, Modus Saugen / Saugen + Wischen / Wischen. Umschalter oben „Sauger | Mäher“.

**Aktionen:** `vacuum.return_to_base`, `button.press`, `vacuum.send_command`, `select.select_option`

<details><summary>Verwendete Entitäten (9)</summary>

- `button.kuche_roborock_qv_35s_nach_mahlzeiten`
- `image.kuche_roborock_qv_35s_erdgeschoss`
- `select.roborock_qv_35s_reinigungsmodus`
- `sensor.roborock_qv_35s_aktueller_raum`
- `sensor.roborock_qv_35s_batterie`
- `sensor.roborock_qv_35s_reinigungsfortschritt`
- `sensor.roborock_qv_35s_status`
- `vacuum.pause`
- `vacuum.roborock_qv_35s`

</details>

## Mäher (`/maeher`)

Worx-Landroid-Mähroboter: Status, zur Station, Kantenschnitt, Akku, nächster Start, Regensensor.

**Aktionen:** `lawn_mower.dock`, `button.press`

<details><summary>Verwendete Entitäten (10)</summary>

- `binary_sensor.maehroboter_ladevorgang`
- `binary_sensor.maehroboter_mqtt`
- `binary_sensor.maehroboter_regensensor`
- `button.maehroboter_kantenschnitt`
- `lawn_mower.maehroboter`
- `lawn_mower.pause`
- `lawn_mower.start_mowing`
- `sensor.maehroboter_batterie`
- `sensor.maehroboter_fehler`
- `sensor.maehroboter_nachster_zeitplan`

</details>

## Ring (`/ring`)

Ring-Türklingel: Livebild, Klingel- und Bewegungsstatus, Bewegungserkennung ein/aus sowie der Türkontakt der Eingangstür.

<details><summary>Verwendete Entitäten (5)</summary>

- `binary_sensor.eingangstur_contact`
- `binary_sensor.haustur_ding`
- `binary_sensor.haustur_motion`
- `camera.haustur_live_ansicht`
- `switch.haustur_bewegungserkennung`

</details>

## Musik (`/musik`)

Radio über Alexa-Lautsprecher: Ziel wählen (Wohnzimmer, Küche, Bad), Sender Radio Lippe, WDR 4 oder Spotify, Stopp und Lautstärke.

**Aktionen:** `input_select.select_option`, `script.turn_on`

<details><summary>Verwendete Entitäten (7)</summary>

- `input_select.radio_ziel`
- `media_player.bad_echo_dot_bad`
- `media_player.kuche_echo_show_kuche`
- `media_player.wohnzimmer_polk_command_bar_wohnzimmer`
- `script.radio_lautstaerke`
- `script.radio_starten`
- `script.radio_stopp`

</details>

## Wetter (`/wetter`)

Aktuelles Wetter und Vorhersage (Met.no) mit Luftfeuchte, Wind, Druck und Wolken.

<details><summary>Verwendete Entitäten (1)</summary>

- `weather.forecast_home`

</details>

## Gemeinsame Bausteine

- **`button_card_templates`** (oben in beiden YAML-Dateien): wiederverwendbare Vorlagen für Kacheln, Kopfzeile und Navigationsleiste. Fast alle Karten bauen darauf auf.
- **`kiosk_mode`** (nur Wall): blendet Kopf- und Seitenleiste bis 500 px Breite aus.
- **`swipe_nav`**: Wischen zwischen den Ansichten.
- Layout über `custom:grid-layout` (layout-card) mit festen Rasterflächen.

## Externe Abhängigkeiten

- Sungrow-Wechselrichter und -Wallbox über Modbus (Entitäten `set_ac_wb_*`, `set_wb_*` aus dem Projekt [mkaiser/Sungrow-SHx-Inverter-Modbus-Home-Assistant](https://github.com/mkaiser/Sungrow-SHx-Inverter-Modbus-Home-Assistant))
- Integrationen: EcoFlow, ViCare, Roborock, Landroid Cloud, Ring, Alexa Media Player, Home Connect, Forecast.Solar, Met.no, Shelly, Tuya/Zigbee2MQTT
- Alles Weitere (Helfer, Skripte, Template-Sensoren, Automationen) steht in [`packages/dashboard_helpers.yaml`](../packages/dashboard_helpers.yaml).
