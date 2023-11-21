# Kapitel 6: Sensoren auslesen

![Kapitelbild](bilder/kap_06_kapitelbild.png)

In this chapter ...

- ... you will connect a temperature sensor to your Raspberry Pi.
- ... you will get the values ot the temperature sensor in a script.

---

#!/usr/bin/python

import os
import time

def get_temperature():
    # Pfad zum DS18B20-Temperatursensor
    sensor_path = "/sys/bus/w1/devices/28-XXXXXXXXXXXX/w1_slave"  # Ersetze XXXXXXXXXXXX durch die tatsächliche ID deines Sensors

    # Datei mit den Sensorwerten öffnen
    try:
        with open(sensor_path, 'r') as sensor_file:
            lines = sensor_file.readlines()
            # Temperaturwert aus den Sensorwerten extrahieren
            temperature = float(lines[1].split('=')[1]) / 1000.0
            return temperature
    except IOError as e:
        print(f"Fehler beim Lesen des Sensors: {e}")
        return None

def main():
    try:
        counter = 0
        while True:
            temperature = get_temperature()
            if temperature is not None:
                print(f"Aktuelle Temperatur: {temperature} °C")

            time.sleep(1)
            counter += 1

            # Hinweis nach jedem 3. Anzeigen der Temperatur
            if counter == 3:
                print("Das Programm kann mit STRG+C beendet werden.")
                counter = 0

    except KeyboardInterrupt:
        print("\nProgramm wurde beendet.")

if __name__ == "__main__":
    main()

Natürlich, hier ist eine Beschreibung jeder Zeile des Python-Skripts für den DS18B20-Temperatursensor:

```python
import os
import time
```

1. `import os`: Importiert das Betriebssystemmodul, das für den Zugriff auf das Dateisystem verwendet wird.
2. `import time`: Importiert das `time`-Modul, das für Zeitverzögerungen verwendet wird.

```python
def get_temperature():
    # Pfad zum DS18B20-Temperatursensor
    sensor_path = "/sys/bus/w1/devices/28-XXXXXXXXXXXX/w1_slave"
    # Ersetze XXXXXXXXXXXX durch die tatsächliche ID deines Sensors
```

3. `def get_temperature():`: Definiert eine Funktion namens `get_temperature`, die die Temperatur des DS18B20-Sensors ausliest.
4. `sensor_path = "/sys/bus/w1/devices/28-XXXXXXXXXXXX/w1_slave"`: Setzt den Pfad zur Datei, die die Rohdaten des Temperatursensors enthält. Ersetze `XXXXXXXXXXXX` durch die tatsächliche ID deines Sensors.

```python
    try:
        with open(sensor_path, 'r') as sensor_file:
            lines = sensor_file.readlines()
            temperature = float(lines[1].split('=')[1]) / 1000.0
            return temperature
    except IOError as e:
        print(f"Fehler beim Lesen des Sensors: {e}")
        return None
```

5. `with open(sensor_path, 'r') as sensor_file:`: Öffnet die Datei im Lesemodus und schließt sie automatisch nach dem Block.
6. `lines = sensor_file.readlines()`: Liest die Zeilen aus der Datei und speichert sie in der Variable `lines`.
7. `temperature = float(lines[1].split('=')[1]) / 1000.0`: Extrahiert den Temperaturwert aus den Sensorwerten und konvertiert ihn von Milligrad Celsius in Grad Celsius.
8. `except IOError as e:`: Fangt einen `IOError` ab, falls beim Lesen des Sensors ein Fehler auftritt.

```python
def main():
    try:
        counter = 0
        while True:
            temperature = get_temperature()
            if temperature is not None:
                print(f"Aktuelle Temperatur: {temperature} °C")

            time.sleep(1)
            counter += 1

            if counter == 3:
                print("Das Programm kann mit STRG+C beendet werden.")
                counter = 0
    except KeyboardInterrupt:
        print("\nProgramm wurde beendet.")
```

9. `def main():`: Definiert die Hauptfunktion des Programms.
10. `counter = 0`: Initialisiert einen Zähler für die Anzahl der Temperaturanzeigenschleifen.
11. `while True:`: Startet eine Endlosschleife für die kontinuierliche Temperaturanzeige.
12. `temperature = get_temperature()`: Ruft die Funktion `get_temperature` auf, um die Temperatur zu erhalten.
13. `if temperature is not None:`: Überprüft, ob die Temperatur erfolgreich gelesen wurde.
14. `time.sleep(1)`: Pausiert für eine Sekunde zwischen den Temperaturmessungen.
15. `counter += 1`: Inkrementiert den Zähler.
16. `if counter == 3:`: Überprüft, ob der Zähler 3 erreicht hat (nach jedem 3. Anzeigen der Temperatur).
17. `print("Das Programm kann mit STRG+C beendet werden.")`: Gibt einen Hinweis aus, dass das Programm mit STRG+C beendet werden kann.
18. `except KeyboardInterrupt:`: Behandelt die Unterbrechung durch den Benutzer (z.B., durch Drücken von STRG+C).
19. `print("\nProgramm wurde beendet.")`: Gibt eine Abschlussmeldung aus.

## Situation

{%
   include-markdown "inhalte/lizenzhinweis.md"
   start="<!--Lizenzhinweis-->"
   end="<!--Lizenzhinweis-->"
%}