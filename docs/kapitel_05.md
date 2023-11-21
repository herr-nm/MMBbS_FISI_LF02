# Kapitel 5: Aktoren ansteuern

![Kapitelbild](bilder/kap_05_kapitelbild.png)

In this chapter ...

- ... you will connect a LED to your Raspberry Pi.
- ... you will use different methods to controll the LED.

---

## Situation
https://makeabilitylab.github.io/physcomp/arduino/rgb-led.html

from gpiozero import LED
import time

# GPIO-Pin für die LED
led_pin = 17  # Hier den tatsächlichen GPIO-Pin anpassen

# Definition von Morsecode für die Buchstaben M, B und S
morse_code = {'M': '--', 'B': '-...', 'S': '...'}


def blink_morse_code(letter):
    for symbol in morse_code[letter]:
        if symbol == '-':
            led.on()
            time.sleep(0.3)
        elif symbol == '.':
            led.on()
            time.sleep(0.1)
        led.off()
        time.sleep(0.1)


def main():
    try:
        led = LED(led_pin)
        for letter in "MMBBS":
            blink_morse_code(letter)
            # Pause zwischen den Buchstaben
            time.sleep(0.5)
    except KeyboardInterrupt:
        print("\nProgramm wurde beendet.")
    finally:
        # Stelle sicher, dass die LED am Ende ausgeschaltet wird
        if 'led' in locals() and led is not None:
            led.off()

if __name__ == "__main__":
    main()


Natürlich, hier ist eine Beschreibung jeder Zeile des Codes:

1. `from gpiozero import LED`: Hier wird die `LED`-Klasse aus der `gpiozero`-Bibliothek importiert, die die Steuerung von LEDs über GPIO-Pins erleichtert.

2. `import time`: Importiert das `time`-Modul, das für die Pausen zwischen den LED-Blinksequenzen verwendet wird.

3. `led_pin = 17`: Der GPIO-Pin, an dem die LED angeschlossen ist, wird auf 17 festgelegt. Du solltest dies an den tatsächlichen GPIO-Pin anpassen.

4. `morse_code = {'M': '--', 'B': '-...', 'S': '...'}`: Definiert ein Wörterbuch (`morse_code`), das den Morsecode für die Buchstaben 'M', 'B' und 'S' enthält.

5. `def blink_morse_code(letter):`: Hier wird eine Funktion `blink_morse_code` definiert, die den Morsecode für einen einzelnen Buchstaben verarbeitet und die LED entsprechend blinken lässt.

6. `for symbol in morse_code[letter]:`: Iteriert über jeden Morsecode-Symbol (Punkt oder Strich) des aktuellen Buchstabens.

7. `if symbol == '-':`, `elif symbol == '.':`, `led.off()`, `time.sleep(0.1)`: Steuert das Ein- und Ausschalten der LED gemäß dem Morsecode-Symbol und fügt Pausen hinzu.

8. `def main():`: Definiert die Hauptfunktion, die die LED für die Buchstaben 'MMBBS' im Morsecode blinken lässt.

9. `led = LED(led_pin)`: Initialisiert die LED mit dem angegebenen GPIO-Pin.

10. `for letter in "MMBBS":`: Iteriert über die Buchstaben 'M', 'M', 'B', 'B', 'S'.

11. `blink_morse_code(letter)`: Ruft die Funktion auf, um den Morsecode für jeden Buchstaben zu blinken.

12. `time.sleep(0.5)`: Pausiert für eine kurze Zeit zwischen den Buchstaben.

13. `except KeyboardInterrupt:` und `finally:`: Behandelt die Unterbrechung durch den Benutzer (z.B., durch Drücken von STRG+C) und stellt sicher, dass die LED am Ende ausgeschaltet wird.

14. `if __name__ == "__main__":`: Sorgt dafür, dass der Code nur ausgeführt wird, wenn das Skript direkt ausgeführt wird, nicht wenn es in einem anderen Skript importiert wird.

15. `main()`: Ruft die Hauptfunktion auf, um den Hauptteil des Programms auszuführen.

{%
   include-markdown "inhalte/lizenzhinweis.md"
   start="<!--Lizenzhinweis-->"
   end="<!--Lizenzhinweis-->"
%}