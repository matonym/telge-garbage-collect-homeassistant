# Telge garbage collect for Homeassistant

Installation:
1. Ladda ner telgesopor.yaml
2. Redigera telgesopor.yaml och ändra "HEMMAVÄGEN 1, STAD" till din gatuadress, stad
```yaml
input_text:
  garbage_collection_address:
    name: Sophämtning Adress
    initial: "HEMMAVÄGEN 1, SÖDERTÄLJE"
```
3. Lägg den i mappen packages
4. Lägg till i configuration.yaml:
```yaml
homeassistant:
  packages: 
    telgesopor: !include /config/packages/telgesopor.yaml
```
5. Starta om Homeassistant
   
Dessa sensorer skapas:
* **sensor.sophamtning** - Sensor med nedastående sensorvärden som attribut
* **binary_sensor.sophamtning_idag** - En presence sensor som rapporterar hemma om sophämtningen är idag.
* **sensor.sophamtning_titel** - Titel t.ex. "Hämtning av hemsortering (370 liters kärl 1)"
* **sensor.sophamtning_karl_id** - Kärlets id, t.ex. "18A"
* **sensor.sophamtning_avfallstyp** - Typ av avfall, t.ex. "HEMSORT"
* **sensor.sophamtning_datum** - Datum för nästa hämtning, t.ex. "2025-02-28"
