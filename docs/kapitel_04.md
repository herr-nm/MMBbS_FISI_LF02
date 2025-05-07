# Kapitel 4: IT-Systeme in Betrieb nehmen

![Kapitelbild](bilder/04_kapitelbild.png)

In diesem Kapitel werden Sie ...

- Vorbereitungen für die Inbetriebnahme eines IT-Systems treffen.
- ein passendes Betriebssystem auswählen.
- die Linux-Kommandozeile nutzen, um ein IT-System zu bedienen
- ein Betriebssystem installieren und aktualisieren.
- die Funktionstüchtigkeit eines IT-Systems prüfen.
- den Inbetriebnahmeprozess dokumentieren und auswerten.

---

## Handlungssituation

Für den unternehmensinternen Auftrag der Change IT GmbH, eine Temperaturmesseinrichtung für die Arbeitsplätze einzurichten, wurde vor einigen Wochen eine Bestellung für die benötigte Hardware getätigt. Der Wareneingang hat diese angenommen und äußerlich auf Schäden kontrolliert. Ihre Aufgabe sind die Vorbereitungen für den Einsatz sowie wie Inbetriebnahme des IT-Systems durchzuführen. Hieran anschließend soll die Funktionstüchtigkeit des IT-Systems getestet werden.

![Raspberry Pi Nahaufnahme](bilder/kap_04_rpi.jpg)

---

## Kompetenz 4.0: Vorbereitungen der Inbetriebnahme eines IT-Systems treffen

Die Hardware ist durch die Warenannahme der Change IT angenommen und innerbetrieblich weitergeleitet worden. Bei Anlieferung wurde lediglich die Überprüfung des korrekten Warenempfängers vorgenommen sowie die Unversehrtheit der Verpackung geprüft.

Der Raspberry Pi und das Zubehör sollen nun in Betrieb genommen werden. Dafür sind die Komponenten richtig zusammenzubauen. Im ersten Schritt sollen die Komponenten des Raspberry Pi und die weiteren Inhalte des Sets genauer betrachtet werden.

![Paket](bilder/kap_04_paket.jpg)

---

### Arbeitsauftrag A|4.0: Kontrolle der Vollständigkeit

#### Aufgabe 1

Breiten Sie das Raspberry Pi-Material vor Ihnen auf dem Tisch aus und fertigen Sie ein Foto an, welches alle Bauteile auf einen Blick enthält.

### Arbeitsauftrag A|4.1: Komponenten des Raspberry Pi erkunden

#### Aufgabe 1

Laden Sie sich aus dem Kursmaterial (M|4.0: Bilder des Raspberry Pi) das zu Ihrem Raspberry Pi passende Bild herunter. Beschriften Sie anschließend die Anschlüsse des Raspberry Pi auf dem Bild.

### Informationsmaterial M|4.0: Bilder des Raspberry Pi

#### Raspberry Pi 5

![RPi 5](bilder/kap_04_rpi5.jpg)

*Quelle des Bildes: https://www.berrybase.de/thumbnail/a1/82/d1/1722543509/RaspberryPi54GBRAM-230062_1920x1920.jpg?ts=1724768071*

#### Raspberry Pi 400

![RPi 400](bilder/kap_04_rpi400.png)

*Quelle des Bildes: https://www.zdnet.com/article/raspberry-pi-400-its-designer-reveals-more-about-the-faster-pi-4-in-the-70-pcs-keyboard/*

#### Raspberry Pi 4B

![RPi 4B](bilder/kap_04_rpi4B.jpg)

*Quelle des Bildes: https://cdn.idealo.com/folder/Product/6628/1/6628198/s1_produktbild_max/raspberry-pi-4-model-b.jpg*

#### Raspberry Pi 3B+

![RPi 3B+](bilder/kap_04_rpi3Bplus.jpg)

*Quelle des Bildes: https://m.media-amazon.com/images/I/81hyqDgm8vL.AC_SL1500.jpg*

### M|4.1a: Produktdatenblatt zum Raspberry Pi 5

[Download Produktdatenblatt RPi 5](material/kap_04_Datenblatt_RPi_5.pdf)

### M|4.1b: Produktdatenblatt zum Raspberry Pi 400

[Download Produktdatenblatt RPi 400](material/kap_04_Datenblatt_RPi_400.pdf)

### M|4.1c: Produktdatenblatt zum Raspberry Pi 4B

[Download Produktdatenblatt RPi 4B](material/kap_04_Datenblatt_RPi_4B.pdf)

### M|4.1d: Produktdatenblatt zum Raspberry Pi 3B+

[Download Produktdatenblatt RPi 3B+](material/kap_04_Datenblatt_RPi_3Bplus.pdf)

### Arbeitsauftrag A|4.2: Fragen zum Raspberry Pi

Ein Praktikant der ChangeIT GmbH soll Sie bei dem Raspberry Pi-Projekt unterstützen. Dabei sind im Gespräch folgende Fragen aufgekommen. Beantworten Sie diese jeweils mithilfe des Materials im Kurs (M|4.2: Raspberry Pi - Grundlagen der Energieversorgung / Stromversorgung) begründet in einem kurzen Satz:

#### Aufgabe 1

Mit welcher Ausgangsspannung arbeitet das Netzteil für den Raspberry Pi?

#### Aufgabe 2

Welche Spannung(en) kann der Raspberry Pi über die GPIO-Pins an Bauteile ausgeben?

#### Aufgabe 3

Welche Stromstärke sollte ein Netzteil für den Raspberry Pi 4 (bzw. 3) mindestens liefern?

#### Aufgabe 4

Darf der Raspberry Pi mit einem Netzteil betrieben werden, welches 4 A liefert?

#### Aufgabe 5

Darf der Raspberry Pi mit einem Netzteil betrieben werden, welches 12 V liefert?

#### Aufgabe 6

Wie hoch ist die sichere Stromstärke für den Gesamtstrom aller GPIO?

#### Aufgabe 7

Wie hoch ist die sichere Stromstärke für einen einzelnen GPIO im Optimum?

### M|4.2: Raspberry Pi - Grundlagen der Energieversorgung / Stromversorgung

#### Grundlagen der Energieversorgung

Mini-Computer, wie der Raspberry Pi, bedürfen einer stabilen Spannungs- UND Stromversorgung. Bei einem schlechten Netzteil und ungünstigen Betriebsbedingungen treten merkwürdige Effekte in Kombination mit einem instabilen Systemverhalten auf. Oftmals sind dies abbrechende LAN- und WLAN-Verbindungen und anderweitiges Fehlverhalten von Geräten, die per USB angeschlossen sind.

Raspberry Pi sind auf eine stabilisierte Betriebsspannung von in der Regel ca. 5 Volt angewiesen. Wenn der Raspberry Pi mit einem beliebigen Steckernetzteil betrieben wird, dann kann und wird das in der Regel funktionieren. Wenn jetzt aber der Raspberry Pi und angeschlossene USB-Geräte für eine impulsive Stromentnahme sorgen, dann kann es vorkommen, dass das Steckernetzteil überfordert ist, aussetzt und die Spannung daraufhin einbricht. Also deutlich unter 5 Volt fällt.

Was passiert dann? Ein Gerät, das für 5 Volt konzipiert ist, kommt dann in einen instabilen Betriebszustand. Hinzu kommt, dass USB-Geräte 5 Volt am USB-Port erwarten. Laut USB-Spezifikation sollte ein USB-Gerät zwischen 4,45 und 5,5 Volt funktionieren.

Bei Unterspannung nimmt der Raspberry Pi seine USB-Ports außer Betrieb, um die Stabilität der Stromversorgung durch Reduzierung der Stromentnahme wieder herzustellen. Dabei gehen zumindest kurzzeitig alle USB-Geräte außer Betrieb. Und das führt dann eben zu besagten Fehlfunktionen einzelner USB-Geräte oder des gesamten Systems und erklärt die Aussetzer bei den USB-Geräten. Das betrifft Maus, Tastatur, WLAN- und LAN-Verbindungen, sowie USB-Speichergeräte.

Grundsätzlich wird der Raspberry Pi mit einer Spannung von 5 Volt am Micro-USB-Eingang mit Energie versorgt. Genau genommen sind es 5,1 V, was die meisten USB-Steckernetzteile auch liefern. Es sind deshalb 5,1 V, weil durch Steckverbindungen und Leitungen Verluste entstehen.

Der zweite wichtige Wert bei der Energieversorgung ist der Stromverbrauch, der in Ampere angegeben wird. Wie viel Strom der Raspberry Pi genau braucht hängt davon ab, was daran angeschlossen ist. In der Regel reicht ein Netzteil mit 2,5-3 A (je nach Raspberry Pi) aus. Aber nur dann, wenn man keine stromhungrigen USB-Geräte anschließt. Dann braucht man einen extern gespeisten USB-Hub oder sollte ein Netzteil mit mindestens 2,5 A verwenden. Wichtig ist zu wissen, mehr als 2,5 A kann ein Raspberry Pi nicht ziehen. Wenn das Gesamtsystem mehr Strom braucht, dann wird das durch eine Sicherung begrenzt und zu Instabilitäten führen kann.

Netzteile werden für den Betrieb in der Regel ca. 20 bis 30 % überdimensioniert. Unter Dauerlast bei voller Auslastung kann es zu Problemen für das Netzteil kommen.

Stromversorgung: Raspberry Pi 3B
Speziell beim Raspberry Pi 3 sollte man wissen, dass dieser über einen Konstruktionsfehler verfügt. Wegen eines neuen Leiterplattendesigns und Einsparungen beim Einsatz minderwertiger Bauteile fallen auf dem Weg zwischen Micro-USB-Buchse und dem Chip bis zu 0,6 Volt ab. Das führt dazu, dass der Raspberry Pi 3 mit einem herkömmlichen USB-Netzteil mit 5,1 V an der Grenze der Unterspannung betrieben wird. Das Problem wird dadurch behoben, dass das offizielle Netzteil für den Raspberry Pi 3 eine Spannung von 5,2 Volt hat.

Stromversorgung: Raspberry Pi 4B
Im Gegensatz zu den Modellen davor braucht der Raspberry Pi 4B ein USB-Netzteil mit 5 Volt und 3 Ampere mit USB-Typ-C (Steckverbindung). Hierbei muss beachtet werden, dass beim Raspberry Pi 4B der USB-C-Port fehlerhaft implementiert ist und aktive USB-C-Kabel (mit E-Mark-Chip) den Raspberry Pi 4B als Audio-Adapter erkennen und deshalb keinen Strom ausgeben.

Abhilfe schafft ein einfaches USB-C-Kabel ohne den E-Mark-Chip. Solche Kabel liegen meist als Ladekabel für Smartphones bei. Die üblichen Kabel für Notebooks, Thunderbold usw. sind für den Betrieb des Raspberry Pi 4B nicht geeignet. Die Raspberry Pi Foundation hat eine Revision angekündigt, weshalb es neuere Raspberry Pi 4B gibt, bei der dieses Problem nicht besteht.

*Quelle: https://www.elektronik-kompendium.de/sites/raspberry-pi/1912111.htm*

#### Maximale Stromstärke der GPIO

Eines vorneweg, der Gesamtstrom aller GPIOs sollte 50 mA nicht übersteigen. Denn das ist die größte Stromstärke (mit Reserve natürlich) die ein Bond (das dünne Drähtchen vom "Beinchen" des Schaltkreises zur eigentlichen internen Schaltung) aushalten kann.

Die gesamte Elektronik eines (einzelnen) Anschlusses ist für maximal 16 mA ausgelegt. Das heißt, es treten bis 16 mA keine Schäden auf. Alles darüber ist unsicher. Auch wenn der eine oder andere Bastler deutlich mehr aus einem GPIO bekommt.
Der Bereich, in dem die Ausgangsendstufen eines GPIO sicher arbeiten reicht von 2 bis 16 mA. Als Optimum liegt zwischen 3 und 8 mA. Mit mehr als 8 mA sollte man nicht rechnen. Aber auch nicht weniger als 2 mA.

*Quelle: https://www.elektronik-kompendium.de/sites/raspberry-pi/2006031.htm*

## Kompetenz 4.1: Betriebssystem auswählen

Für die Temperatur-Messeinheit der Change IT GmbH soll ein Raspberry Pi eingesetzt werden. Nicht jedes Linux-Betriebssystem kann auf dem Raspberry Pi installiert werden. Für diesen stehen allerdings verschiedene spezialisierte Betriebssysteme zur Verfügung. Sie wollen sich einen Überblick zu den Linux-Varianten verschaffen, um ein passendes System auszuwählen. Nach der Einrichtung der Temperatur-Messeinheiten werden die Raspberry Pi ferner nicht mehr per Bildschirm, Maus und Tastatur bedient. Vielmehr ist eine Remote-Bedienung vorgesehen. Auch hierzu fehlen noch Informationen, bevor das IT-System in Betrieb genommen werden kann.

![Linux Pinguin](bilder/kap_04_penguin.png)

### A|4.4: Linux-Distributionen unterscheiden

#### Aufgabe 1

Was sind Linux-Distributionen (s. M|4.4: Linux-Distributionen im Überblick)? Beschreiben Sie in eigenen Worten.

### M|4.4: Linux-Distributionen im Überblick

Bei Windows ist die Sache einfach: Hersteller Microsoft bringt eine neue Version raus und zeitweise gibt es noch den Vorgänger - das war es auch schon an Auswahl. Bei Linux sieht die Sache etwas anders aus. Es gibt nämlich nicht "das Linux". Genau genommen müsste man das Ganze sowieso GNU/Linux nennen: Was man gemeinhin Linux nennt, besteht aus einem Kernel, eben Linux, und einer Reihe von Standard-Werkzeugen, den GNU Tools. Aber lassen wir das mal beiseite und sprechen wie üblich einfach von Linux. Diese Kernelemente finden Sie in allen Linuxen, genauer gesagt Linux-Distributionen, kurz Distris genannt. Da die Linux-Basis Open Source Software ist, kann sich jeder ein eigenes System basteln und distribuieren - daher der Name Distri.

Und genau dort liegen die großen Unterschiede: Wer entwickelt das System? Was kommt in das System? Wie wird veröffentlicht? Welche zusätzlichen Tools gehören dazu? Und wie genau sieht der Desktop aus? Manche Distris werden hauptsächlich von dahinter stehenden Firmen herausgegeben, etwa Ubuntu von Canonical oder Red Hat Enterprise Linux von Red Hat. Andere Distributionen sind komplett Community-betreut, allen voran Debian. Die meisten großen Distris spendieren Ihren Linuxen auch eigene Tools rund um das System - insbesondere das, was man unter Windows als "Systemsteuerung" kennt, löst jede Distri auf eigene Art. Die "großen" Anwendungsprogramme wie Office (LibreOffice) oder Bildbearbeitung (Gimp) finden sich natürlich überall. Wichtig ist dabei auch, wie ernst die Projekte den Freiheitsgedanken nehmen: Wo Debian standardmäßig nur auf freie, quelloffene Software setzt, baut Ubuntu auch unfreie Software ein, beispielsweise Grafikkartentreiber oder Multimedia-Codecs. Auch die Update-Politiken unterscheiden sich: Teils wird zu fixen Terminen veröffentlicht, teils landen aktualisierte Pakete kontinuierlich in den so genannten Repositories. Apropos: Jede Distri hat ein solches dazugehörige "Repo", aus dem sich über das Paketmanagement ganz einfach Programme installieren lassen - Debian kommt auf über 50.000 Pakete.

Für die meisten Heimanwender stellt sich vor allem eine Frage: Wie sieht der Desktop aus? Bei Windows sind OS und Desktop untrennbar verbunden, bei Linux ist die gesamte Desktop-Umgebung im Grunde nur ein Anwendungsprogramm, das nach Belieben installiert und ausgetauscht werden kann. Alle Systeme haben einen Standard-Desktop, aber man kann ihn auswechseln. Bestes Beispiel: Ubuntu gibt es auch als Lubuntu, Kubuntu und Xubuntu, was für die Standard-Desktops LXDE, KDE und XFCE steht. Zwar verändern die Projektteams hier und da auch noch andere Details, aber im Grunde könnten Sie einfach Ubuntu aufsetzen und dann LXDE, KDE (heute Plasma) und XFCE installieren - und beim Start wählen Sie dann das gewünschte System.

Nicht alle Aspekte sind für jeden wichtig, aber damit haben Sie schon mal eine Grundlage für die Auswahl. Lässt man die Technik mal außen vor, unterscheiden sich die Distris aus Nutzersicht in Fragen wie: Wie schlank ist das System? Wie komfortabel? Wie frei? Wie gut dokumentiert?

![Linux Stammbaum](bilder/kap_04_LinuxStammbaum.png)

*Quellen:*
- *https://www.heise.de/tipps-tricks/Linux-Betriebssysteme-eine-Uebersicht-4119937.html*
- *https://codezentrale.de/linux-stammbaum-linux-distributionen/*

---

### A|4.5: Linux-Systeme remote bedienen

Informieren Sie sich mithilfe des Materials im Kurs (M|4.5: SSH, VNC und Telnet) und beantworten Sie die folgenden Fragen:

#### Aufgabe 1

Was ist eine SSH-Verbindung?

#### Aufgabe 2

Welche Software wird für den Aufbau einer SSH-Verbindung auf der Client- sowie auf der Server-Seite benötigt?

#### Aufgabe 3

Was ist der Unterschied zwischen SSH und VNC?

#### Aufgabe 4

Was ist der Unterschied zwischen SSH und Telnet?

#### Aufgabe 5

Welche Vor- und Nachteile hat eine Remote-Wartung gegenüber einer Vor-Ort-Wartung von IT-Systemen?

### M|4.5: Secure Shell (SSH) und Virtual Network Computing (VNC)

#### Secure Shell (SSH)

Secure Shell (SSH) ist ein Netzwerkprotokoll, das entwickelt wurde, um eine sichere Kommunikation über ein unsicheres Netzwerk zu ermöglichen. Typischerweise wird SSH verwendet, um eine verschlüsselte Verbindung zu einem entfernten Server herzustellen und so eine sichere Datenübertragung, Authentifizierung und Interaktion mit dem entfernten System zu gewährleisten.

![SSH Protokoll Wikipedia](bilder/kap_04_ssh.png)

*Bildquelle: https://de.wikipedia.org/wiki/Secure_Shell*

- **Verschlüsselte Verbindungen:** SSH verschlüsselt die Kommunikation zwischen dem Client und dem Server, was bedeutet, dass sensible Daten wie Passwörter, Befehle und Dateiübertragungen vor unbefugtem Zugriff geschützt sind.
- **Authentifizierung:** SSH ermöglicht die sichere Authentifizierung von Benutzern, um sicherzustellen, dass nur autorisierte Personen auf das System zugreifen können. Dies kann durch Passwörter, Schlüsselpaare oder andere Authentifizierungsmethoden erfolgen.
- **Sichere Datenübertragung:** Dateien können sicher über SSH übertragen werden. Dies wird oft durch den Einsatz von SCP (Secure Copy) oder SFTP (Secure File Transfer Protocol) erreicht.
- **Portabilität:** SSH ist plattformunabhängig und kann auf verschiedenen Betriebssystemen wie Linux, macOS und Windows verwendet werden.
- **Remote-Shell-Zugriff:** Eines der Hauptanwendungsgebiete von SSH ist der Zugriff auf eine Remote-Shell auf einem entfernten Server. Dies ermöglicht es Benutzern, Befehle auf einem entfernten System auszuführen, als ob sie direkt vor dessen Bildschirm sitzen würden.

**Aufbau einer SSH-Verbindung**

Sie benötigen in der Regel keine zusätzliche Software. Ein Terminal-Fenster Ihres Betriebssystems reicht hierfür aus.

Mit dem Befehl `ssh pi@172.20.20.20` verbinden Sie sich als Benutzer `pi` via SSH mit dem Remote-System, welches im Beispiel die IP `172.20.20.20` hat.

#### Virtual Network Computing

![VNC](bilder/kap_04_vnc.png)

Virtual Network Computing (VNC) ist eine Technologie, die es ermöglicht, den Bildschirminhalt eines Computers über ein Netzwerk zu übertragen und die Tastatureingaben und Mausbewegungen von einem entfernten Standort aus zu steuern. Mit VNC kann ein Benutzer von einem Computer aus auf einen anderen Computer zugreifen, als ob er direkt vor diesem sitzen würde. Die Technologie ermöglicht Remote-Desktop-Zugriff und -kontrolle.

- **Server:** Auf dem Computer, dessen Bildschirminhalt freigegeben werden soll, muss ein VNC-Server installiert und gestartet werden. Der VNC-Server erfasst den Bildschirminhalt und wartet auf eingehende Verbindungen.
- **Client:** Der Computer, der auf den entfernten Bildschirminhalt zugreifen möchte, benötigt einen VNC-Client. Dieser Client stellt eine Verbindung zum VNC-Server her und empfängt die übertragenen Bildschirminhalte.
- **Übertragungsprotokoll:** VNC verwendet ein spezifisches Protokoll (z. B. RFB - Remote Framebuffer Protocol), um den Bildschirminhalt zu übertragen und Benutzereingaben zu steuern. Dieses Protokoll ermöglicht die Übertragung von Grafiken, Mausbewegungen und Tastatureingaben über das Netzwerk.
- **Verschlüsselung (optional):** In einigen VNC-Implementierungen kann eine Verschlüsselung aktiviert werden, um die übertragenen Daten zu schützen. Dies ist besonders wichtig, wenn VNC über unsichere Netzwerke wie das Internet verwendet wird, um die Privatsphäre und Sicherheit zu gewährleisten.

### Telnet

Telnet steht für "Telecommunication Network" und ist ein Netzwerkprotokoll, das für die remote textbasierte Kommunikation zwischen Computern über ein TCP/IP-Netzwerk verwendet wird. Es wurde ursprünglich für den Zugriff auf entfernte Systeme und die Fernadministration entwickelt. Telnet ermöglicht es einem Benutzer, von einem Computer aus eine Verbindung zu einem anderen Computer herzustellen und eine Eingabeaufforderung oder ein Terminalfenster auf dem entfernten System zu öffnen.

Es ist wichtig zu beachten, dass Telnet in seiner grundlegenden Form keine Verschlüsselung für die übertragenen Daten bietet. Alle Informationen, einschließlich Benutzernamen und Passwörtern, werden im Klartext über das Netzwerk übertragen. Aus diesem Grund ist die Verwendung von Telnet über unsichere Netzwerke, wie das Internet, nicht ratsam, da es ein erhebliches Sicherheitsrisiko darstellt. Unautorisierte Personen könnten den Netzwerkverkehr mithören und sensible Informationen abfangen.

Aufgrund der Sicherheitsbedenken wird Telnet heute oft durch sicherere Alternativen wie SSH (Secure Shell) ersetzt, das eine verschlüsselte Verbindung für die Remote-Administration bietet und somit die Integrität und Vertraulichkeit der übertragenen Daten gewährleistet.

## Kompetenz 4.2: Linux-Kommandozeile bedienen

Die IT-Abteilung der Change IT GmbH hat sich bei den eingesetzten IT-Systemen für die Wartung und Konfiguration via SSH entschieden. Hierbei fallen Standardaufgaben an, die eine Bedienung des Linux-Systems mit sich bringt. Kurz danach erhalten Sie den Auftrag ein Remote-System mit dem Betriebssystem Raspberry Pi OS (x86) für ein Projekt vorzubereiten und zu testen.

![Linux-Terminal Symbolbild](bilder/kap_04_linux.png)

### Arbeitsauftrag A|4.6: Linux-Befehlsreferenz anlegen

**Aufgabe 1**

Ihnen liegt ein vorbereitetes Cheat-Sheet zu Linux-Kommandozeilenbefehlen vor (Vorlage - Cheat Sheet Linux). Dieses ist noch nicht vollständig ausgefüllt, Sie wollen die Übersicht nun fertigstellen, um zukünftig eine Schnellreferenz vorliegen zu haben.Verschaffen Sie sich mithilfe des *Informationsmaterials M|4.6: Linux-Kommandozeilenbefehle* im Kurs einen Überblick zu den wichtigsten Befehlen für die Linux-Kommandozeile und vervollständigen Sie das Cheat-Sheet.

!!! note "Hinweis"
    
    Das Blatt ist in den drei Niveaustufen in Anlehnung an den ISA-Unterricht aufgebaut:
    
    - Einsteiger: Befehle kennen und zuordnen
    - Könner: Befehle situationsgerecht anwenden
    - Profi: Befehlserweiterungen oder Fälle beschreiben können

**Aufgabe 2**

Wenn Sie die Befehlsreferenz fertiggestellt haben, geben Sie diese in dieser Aufgabe als .pdf-Datei (max. 5 MB) ab. Anschließend wird eine Beispiellösung *Lösungshinweis zu A|4.6: Linux-Befehlsreferenz anlegen* freigeschaltet. Gleichen Sie Ihre Lösung mit der Beispiellösung ab. Notieren Sie sich Auffälligkeiten oder Lösungsabweichungen für die spätere Besprechung in der Klasse.

### Informationsmaterial M|4.6: Linux-Kommandozeilenbefehle

#### 📁 Datei- und Verzeichnismanagement

**cd**

Der Befehl `cd` (change directory) dient zum Wechseln in ein anderes Verzeichnis. Er kann mit relativen oder absoluten Pfaden verwendet werden. Mit `cd ..` springt man eine Verzeichnisebene zurück. `cd` ohne Parameter bringt Sie ins Home-Verzeichnis.

*Beispiel:* `cd /home/user/projekt01`

---

**ls**

`ls` listet den Inhalt eines Verzeichnisses auf. Mit `-l` (kleines L) wird eine detaillierte Liste mit Größen, Rechten und Zeitstempeln angezeigt. Die Option -a zeigt auch versteckte Dateien. In Kombination (`ls -la`) ist der Befehl besonders nützlich zur vollständigen Übersicht.

*Beispiel:* `ls -la`

---

**pwd**

`pwd` (print working directory) gibt den vollständigen Pfad zum aktuellen Verzeichnis aus. Das ist besonders hilfreich, um die Orientierung im Dateisystem zu behalten. Der Pfad beginnt immer mit `/`, dem Wurzelverzeichnis. So wissen Sie genau, wo Sie sich befinden.

*Beispiel:* `pwd` → Ausgabe: `/home/user/dokumentation`

---

**mkdir**

Mit `mkdir` (make directory) wird ein neues Verzeichnis erstellt. Die Option `-p` ermöglicht es, auch verschachtelte Ordner in einem Schritt anzulegen. Der Name kann relativ oder absolut sein. Bereits bestehende Ordner führen zu einer Fehlermeldung.

*Beispiel:* `mkdir -p projekt01/code`

---

**rmdir**

`rmdir` löscht leere Verzeichnisse. Wenn sich noch Dateien oder Unterordner darin befinden, bricht der Befehl mit einer Fehlermeldung ab. Für nicht leere Verzeichnisse wäre `rm -r` erforderlich. `rmdir` ist sicher, da es keine Daten versehentlich löscht.

*Beispiel:* `rmdir testordner`

---

**rm**

`rm` entfernt Dateien oder mit der Option `-r` auch ganze Verzeichnisse samt Inhalt. Der Befehl löscht unwiderruflich – es gibt keinen Papierkorb. Bei sensiblen Dateien ist Vorsicht geboten. Mit `-i` kann eine Sicherheitsabfrage aktiviert werden.

*Beispiel:* `rm -r alte_daten`

---

**touch**

Mit `touch` erstellt man leere Dateien. Existiert die Datei bereits, wird lediglich der Zeitstempel aktualisiert. Der Befehl ist nützlich für das schnelle Anlegen von Textdateien oder Platzhaltern.

*Beispiel:* `touch info.txt`

---

**cp**

`cp` (copy) kopiert Dateien oder mit der Option `-r` auch Verzeichnisse. Ziel und Quelle müssen angegeben werden. Der Befehl kann auch verwendet werden, um Sicherungskopien anzulegen.

*Beispiel:* `cp readme.txt backup.txt`

---

**mv**

`mv` verschiebt Dateien oder Ordner – oder benennt sie um. Gibt man einen neuen Dateinamen als Ziel an, wird umbenannt. Gibt man einen Ordner an, wird die Datei dorthin verschoben.

*Beispiel:* `mv alt.txt neu.txt`

---

**nano**

Mit `nano` öffnet man einen einfachen Texteditor direkt im Terminal. Er eignet sich gut zum schnellen Erstellen oder Bearbeiten von Textdateien, z.B. Konfigurationsdateien oder Shell-Skripten. Während der Bearbeitung können die wichtigsten Aktionen über Tastenkombinationen ausgeführt werden: Mit `Strg + O` speichert man die Datei, mit `Strg + X` verlässt man den Editor. Alle Befehle lassen sich jederzeit über `Strg + G` anzeigen.

*Beispiel:* `nano readme.txt`

---

#### 🔒 Rechte und Benutzer

**chmod**

`chmod` ändert die Zugriffsrechte von Dateien und Verzeichnissen. Mit Zahlen wie `755` oder symbolisch (`u+x`) kann genau gesteuert werden, wer was darf. Rechte werden in drei Gruppen vergeben: Eigentümer, Gruppe, andere.

*Beispiel:* `chmod 644 dokumentation/readme.txt`

---

**chown**

`chown` ändert den Eigentümer und optional die Gruppe einer Datei. Nur Administratoren (`root`) dürfen den Eigentümer ändern. Es kann auch rekursiv auf ganze Verzeichnisse angewendet werden.

*Beispiel:* `sudo chown pi:users readme.txt`

---

**adduser**

`adduser` legt einen neuen Benutzer an. Der Befehl fragt nach einem Passwort und zusätzlichen Informationen. Diese Aktion ist nur mit Adminrechten möglich.

*Beispiel:* `sudo adduser max`

---

**deluser**

`deluser` entfernt einen Benutzer vom System. Optional kann mit `--remove-home` auch das Benutzerverzeichnis gelöscht werden. Auch dieser Befehl benötigt Adminrechte.

*Beispiel:* `sudo deluser max`

---

**passwd**

`passwd` ändert das Passwort des aktuellen Benutzers oder (als `root`) eines anderen. Der Befehl fragt das neue Passwort zweimal ab. Auch Benutzer ohne Adminrechte können ihr eigenes Passwort ändern.

*Beispiel:* `passwd`

---

**whoami**

`whoami` zeigt den aktuell angemeldeten Benutzernamen an. Das ist nützlich, um sich zu vergewissern, unter welchem Benutzer man gerade arbeitet.

*Beispiel:* `whoami`

---

#### 🖥️ Systemanalyse und -zustand

**htop**

`htop` zeigt eine Live-Ansicht der aktuell laufenden Prozesse. CPU- und RAM-Auslastung werden ebenfalls dargestellt. Die Übersicht wird laufend aktualisiert.

*Beispiel:* `htop`

**ps aux**

`ps aux` listet alle Prozesse auf, die aktuell auf dem System laufen. Es zeigt Benutzer, PID, CPU-/RAM-Auslastung und die gestarteten Programme. In Kombination mit `grep` kann gezielt gesucht werden.

*Beispiel:* `ps aux | grep nano`

**df -h**

`df -h` zeigt die Belegung der Festplatten an. Die Option `-h` steht für „human readable“ und zeigt Größen in MB/GB. Der Befehl hilft, Speicherengpässe zu erkennen.

*Beispiel:* `df -h`

---

**free -h**

`free -h` zeigt die Belegung des Arbeitsspeichers an. Auch hier bedeutet `-h`, dass die Größen in verständlichen Einheiten angezeigt werden.

*Beispiel:* `free -h`

---

**uname -a**

`uname -a` liefert Systeminformationen, z.B. Kernel-Version, Hostname und Architektur. Es ist besonders nützlich für die Fehlersuche oder bei Updates.

*Beispiel:* `uname -a`

---

**uptime**

`uptime` zeigt an, wie lange das System bereits läuft, wie viele Benutzer angemeldet sind und die durchschnittliche Systemlast.

*Beispiel:* `uptime`

---

**history**

`history` listet alle zuvor eingegebenen Befehle chronologisch auf. Praktisch zur Nachverfolgung und Fehleranalyse. Einzelne Befehle lassen sich per `!Nummer ` erneut ausführen.

*Beispiel:* `history`

---

#### ⚙️ Skripte, Ausgabe, GPIO

**./script.sh**

Ein Shell-Skript wird im Terminal durch Voranstellen von `./` ausgeführt – vorausgesetzt, es ist als ausführbar markiert. Vor dem ersten Start muss bspw. mit `chmod +x` die Ausführungsberechtigung gesetzt werden. Das Skript kann beliebige Befehle enthalten, etwa zur Automatisierung von Aufgaben. Wird `./` nicht verwendet, sucht das System das Skript nicht im aktuellen Verzeichnis.

*Beispiel:* `./script.sh` führt das Skript `script.sh` im aktuellen Ordner aus.

---

**cat**

`cat` zeigt den Inhalt einer Datei im Terminal an. Damit kann man Textdateien schnell durchsehen. Auch nützlich für das Zusammenfügen mehrerer Dateien.

*Beispiel:* `cat readme.txt`

---

**tail**

`tail` zeigt standardmäßig die letzten 10 Zeilen einer Datei. Mit `-n` kann man die Anzahl der Zeilen anpassen. Mit `-f` kann man eine Log-Datei live mitverfolgen.

*Beispiel:* `tail -n 5 readme.txt`

---

**grep**

`grep` durchsucht Texte oder Dateien nach bestimmten Zeichenfolgen. Ideal zum Filtern von Log-Dateien oder Prozessen. Mit `-i` wird die Groß-/Kleinschreibung ignoriert.

*Beispiel:* `grep "Fehler" log.txt`

---

**pinout**

`pinout` zeigt eine grafische Übersicht der GPIO-Pins eines Raspberry Pi (funktioniert nur auf echtem Pi). Alternativ kann https://pinout.xyz genutzt werden.

*Beispiel:* `pinout`

---

**shutdown**

shutdown beendet das System sicher. Optionen wie `-h now` oder `-r +10` ermöglichen das sofortige oder geplante Herunterfahren oder Neustarten. Erfordert meist Adminrechte.

*Beispiel:* `sudo shutdown -h now`

---

**reboot**

`reboot` startet das System neu. Wird häufig für Wartungsarbeiten oder nach Updates verwendet.

*Beispiel:* `sudo reboot`

### Auswahl der Niveaustufe für die Aufgaben zur Arbeit in der Linux-Kommandozeile (A|4.7):

- Standardmäßig ist die Stufe Profi gewählt.
- Benötigen Sie mehr Hilfestellungen, kennzeichnen Sie diese Textbox als "Erledigt", um den *Arbeitsauftrag A|4.7* als Könner anzeigen zu lassen.	

### SSH-Login zum Server

Zur Bearbeitung der folgenden Aufgaben steht Ihnen ein Linux-Server zur Verfügung, der aus dem Schulnetz erreichbar ist:

- IP: wird Ihnen im Unterricht mitgeteilt.
- Port: 22
- Username: wird Ihnen im Unterricht mitgeteilt
- Passwort: wird Ihnen im Unterricht mitgeteilt

### Arbeitsauftrag A|4.7: Linux-Terminal bedienen (Könner)

**Aufgabe 1**

Speichern Sie diese Aufgabenstellungen in einem eigenen Dokument (z.B. Word oder LibreOffice).

**Aufgabe 2**

Arbeiten Sie auf dem bereitgestellten Raspberry Pi OS im Terminal. Verwenden Sie Ihr persönliches Login. Ihre Aufgabe ist es, systematisch Befehle einzugeben, um typische Administrationsaufgaben durchzuführen.

Notieren Sie die von Ihnen verwendeten Befehle unter die jeweiligen Aufgabenpunkte. Nutzen Sie Ihr Cheat Sheet zur Unterstützung.

**1. Verzeichnisse und Dateien verwalten**

- Wechseln Sie in Ihr persönliches Startverzeichnis. Überlegen Sie, mit welchem Befehl Sie sich den aktuellen Pfad anzeigen lassen können.
- Legen Sie einen Projektordner `projekt01` an. Dieser soll später Ihre Übungsdateien enthalten.
- Erstellen Sie darin die Unterordner `code`, `daten` und `dokumentation`. Tipp: Der Befehl kann mehrere Ordner auf einmal anlegen.
- Erzeugen Sie im Ordner `dokumentation` eine leere Textdatei `readme.txt`.
- Bearbeiten Sie die Datei im Terminal. Fügen Sie einen kurzen Text zum Projektthema ein.
- Kopieren Sie die Datei anschließend in den Ordner `daten`. Denken Sie daran, Ziel und Quelle zu benennen.
- Benennen Sie die Datei um oder verschieben Sie sie an eine andere Stelle.
- Erstellen Sie ein weiteres Verzeichnis und entfernen Sie es wieder – einmal als leeres Verzeichnis, einmal mit Inhalt.

**2. Dateiberechtigungen & Benutzerverwaltung**

- Prüfen Sie, welche Berechtigungen die Datei `readme.txt` aktuell hat. Wie sind sie aufgebaut?
- Passen Sie die Rechte so an, dass:
    - Sie selbst lesen und schreiben dürfen,
    - die Gruppe lesen darf
    - andere nur keine Rechte haben.
- Erstellen Sie einen neuen Benutzer mit dem Namen `testuser_[IhreNummer+100]`.
- Übertragen Sie die Eigentümerschaft der Datei auf diesen Benutzer.
- Löschen Sie den erstellten Testbenutzer nach dem Test wieder.

**3. Systemzustand analysieren**

- Verschaffen Sie sich einen Überblick über alle aktuell laufenden Prozesse im System.
- Filtern Sie diese Liste nach dem Programm `systemd`.
- Rufen Sie eine Live-Übersicht der Systemressourcen auf. Wie verlassen Sie diese Ansicht wieder?
- Prüfen Sie, wie viel Festplattenspeicher noch verfügbar ist.
- Sehen Sie sich an, wie viel Arbeitsspeicher genutzt wird.
- Lassen Sie sich technische Informationen über das System anzeigen.
- Finden Sie heraus, wie lange das System bereits läuft.

**4. Skripte & Historie**

- Erstellen Sie im Ordner code eine Datei `hello.sh`, in der eine kurze Begrüßung (`echo "Moin moin!"`) ausgegeben wird.
- Erteilen Sie der Datei die nötigen Rechte, um sie auszuführen.
- Führen Sie das Skript anschließend aus.
- Sehen Sie sich Ihre zuletzt verwendeten Befehle an. Welchen Nutzen hat diese Liste?

**5. Sonstiges & GPIO**

- Lassen Sie sich anzeigen, unter welchem Benutzer Sie aktuell eingeloggt sind.
- Versuchen Sie, die GPIO-Pinbelegung über den Befehl `pinout` aufzurufen (nur auf echtem Raspberry Pi möglich). Falls das nicht funktioniert, informieren Sie sich auf https://pinout.xyz.
- Informieren Sie sich, mit welchen Befehlen man einen Rechner herunterfahren oder neu starten kann. ***Hinweis: Führen Sie diese nicht wirklich aus!***

**Aufgabe 3**

Speichern Sie Ihre Lösung als PDF-Datei (max. 5 MB) und laden Sie sie hier im Kurs hoch.

**Aufgabe 4**

Nach der Abgabe erhalten Sie ein KI-generiertes Feedback. Lesen Sie dieses sorgfältig und notieren Sie sich Rückfragen oder Auffälligkeiten zur Besprechung im Unterricht.

### Arbeitsauftrag A|4.7: Linux-Terminal bedienen (Profi)

**Aufgabe 1**

Kopieren Sie die Aufgabenstellungen s.u. in ein Dokument.

**Aufgabe 2**

Lösen Sie die Aufgaben auf dem zur Verfügung gestellten Raspberry Pi OS unter Nutzung Ihrer individuellen Login-Details. Schreiben Sie die korrekten Befehle als Lösung direkt unter die einzelnen Aufgabenschritte.

**1. Verzeichnisse und Dateien verwalten**

- Navigieren Sie in Ihr Home-Verzeichnis.
- Erstellen Sie den Projektordner `projekt01` mit den Unterordnern `code`, `daten`, `dokumentation`.
- Legen Sie im Ordner `dokumentation` eine leere Datei `readme.txt` an.
- Bearbeiten Sie die Datei mit einem Editor und fügen Sie eine Projektbeschreibung hinzu.
- Kopieren Sie die Datei in den Ordner daten.
- Verschieben oder benennen Sie die Datei anschließend um.
- Löschen Sie testweise ein leeres Verzeichnis.
- Erstellen Sie testweise ein Verzeichnis und löschen Sie es rekursiv.

**2. Dateiberechtigungen & Benutzerverwaltung**

- Prüfen Sie die Rechte der Datei `readme.txt`.
- Setzen Sie die Datei-Berechtigungen so, dass:
    - Der Eigentümer Lese- und Schreibrechte hat,
    - die Gruppe nur Leserechte besitzt und
    - andere gar keine Rechte haben.
- Legen Sie einen neuen Benutzer `testuser_[IhreNummer+100]` an.
- Ändern Sie den Eigentümer der Datei auf `testuser_[IhreNummer+100]`.
- Löschen Sie `testuser_[IhreNummer+100]` nach dem Test wieder.

**3. Systemzustand analysieren**

- Zeigen Sie alle laufenden Prozesse an.
- Filtern Sie die Liste nach dem Programm systemd.
- Starten Sie die Live-Prozessübersicht.
- Lassen Sie sich den verfügbaren Speicherplatz anzeigen.
- Überprüfen Sie die RAM-Auslastung.
- Zeigen Sie System- und Kernelinformationen an.
- Ermitteln Sie die Systemlaufzeit.

**4. Skripte & Historie**

- Erstellen Sie im Ordner `code` ein Skript `hello.sh`, das eine Begrüßung (`echo "Moin moin!"`) ausgibt.
- Machen Sie das Skript ausführbar.
- Führen Sie das Skript aus.
- Prüfen Sie den Verlauf Ihrer bisherigen Befehle.

**5. Sonstiges & GPIO**

- Zeigen Sie Ihren Benutzernamen an.
- Versuchen Sie, pinout aufzurufen (nur auf echtem Raspberry Pi möglich), alternativ: https://pinout.xyz
- Wie würden Sie einen Shutdown und Reboot durchführen? – ***Führen Sie ihn nicht wirklich aus.***

**Aufgabe 3**

Laden Sie Ihre Lösung als .pdf-Datei (max. 5 MB) in dieser Aufgabe hoch.

**Aufgabe 4**

Sie erhalten auf die Lösung ein KI-generiertes Feedback. Analysieren Sie dieses kritisch und notieren Sie sich Auffälligkeiten für die Besprechung in der Klasse.

### Arbeitsauftrag A|4.8: Reflexion der Bedienung eines Remote-Systems via Kommandozeile

**Aufgabe 1**

Beantworten Sie folgende Reflexionsfragen im Textfeld dieser Aufgabe:

- Was haben Sie heute über das Arbeiten mit dem Linux-Terminal gelernt?
- An welcher Stelle waren Sie sich unsicher und wie sind Sie damit umgegangen?
- Welche Befehle oder Funktionen haben Ihnen gefehlt oder welche würden Sie sich gerne genauer ansehen?

## Kompetenz 4.3: Installation und Aktualisierung des Betriebssystems

Der Raspberry Pi ist hardwareseitig einsatzbereit, aktuell fehlt allerdings noch die Software. Die Change IT GmbH nutzt nach Ihrem Vorschlag ein Raspberry Pi OS als Betriebssystem. Dieses wurde in der internen IT-Abteilung bereits so vorbereitet, dass die Endgeräte in das WLAN kommen. Das Betriebssystem steht in einem sogenannten Image bereit. Dieses Image ist eine Momentaufnahme des Betriebssystems, welches auf Micro SD-Karten dupliziert und von dort wieder gestartet werden kann. Nehmen Sie die Installation und erste Aktualisierung auf Ihrem Raspberry Pi vor.

![PC](bilder/kap_04_installation.png)

### A|4.9: Inbetriebnahme des Raspberry Pi

Sie benötigen für die Schritte der Inbetriebnahme folgende Programme:

- Raspberry Pi Imager ([Download](https://www.raspberrypi.org/downloads/))
- MMBbS Raspberry Pi OS Image ([Download](https://mm-bbs.de) über die Landingpage)

Die Anleitung zur Installation des Betriebssystems finden Sie im Kurs.

Wenn Sie diese Aufgabe fertiggestellt haben bestätigen Sie dies über den oben aufgeführten Button:

![Moodle Button](bilder/kap_04_moodle_button.png)

### M|4.7: Inbetriebnahme des Raspberry Pi

<iframe frameborder="0" width="1200" height="675" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;" src="https://view.genial.ly/6019653b31720d0d312eb43c" type="text/html" allowscriptaccess="always" allowfullscreen="true" scrolling="yes" allownetworking="all"></iframe>

## Kompetenz 4.4: Funktionstüchtigkeit eines IT-Systems prüfen

Nach der Installation und Aktualisierung des Betriebssystems ist der Inbetriebnahmeprozess abgeschlossen. Zunächst soll die Funktionstüchtigkeit des Raspberry Pi im Netzwerk überprüft werden. Erst im Anschluss kann das Prototyping mit dem Auslesen von Sensorik starten.

![Laptop](bilder/kap_04_laptop.jpg)

### A|4.10: Basisinformationen zum Raspberry Pi anzeigen

#### Aufgabe 1

Lassen Sie sich die Eckdaten zu Ihrem Raspberry Pi mit dem Befehl "pinout" in der Kommandozeile anzeigen. Welche Informationen können Sie hieraus ablesen?

#### Aufgabe 2

Nutzen Sie in der Kommandozeile den Befehl zur Ausgabe von Netzwerk-Informationen "ifconfig". Geben Sie in eigenen Worten wieder, was Ihnen die Anzeige an Daten ausgibt.

#### Aufgabe 3

Starten Sie mit dem Befehl "htop" den Taskmanager. Verschaffen Sie sich einen groben Überblick über das angezeigte Programm und beschreiben Sie den grundlegenden Aufbau der Ansicht.

## Handlungsergebnis

Sie haben in den letzten Unterrichtsstunden die Inbetriebnahme des Raspberry Pi durchgeführt, sich mit der Bedienung von Linux via Kommandozeile auseinandergesetzt sowie erste technische Informationen aus dem System ausgelesen. An dieser Stelle sollen Sie den aktuellen Standpunkt im Sinne eines Lessons Learned auswerten.

![Protokollant](bilder/kap_04_protokollant.jpg)

### A|4.11: Inbetriebnahme, Installation und Funktionstest auswerten

#### Aufgabe 1

Betrachten Sie den Ablauf der Inbetriebnahme und die ersten Schritte im Betriebssystem mit dem Raspberry Pi. Beantworten Sie die folgenden Fragen:

- Wie zufrieden bin ich mit dem Ergebnis der Inbetriebnahme-Prozesses des Raspberry Pi?
- Was würde ich beim nächsten Installationsprozess anders machen?
- Was hat gut funktioniert und worauf kann ich stolz sein?

# Zusätzliches Material, weitere Übungen und Tipps

## Übungen

### Übung UE|4.3: Speichermaßeinheiten unter Linux anzeigen

**Vorbereitungen für diese Aufgaben**

Sie benötigen für die folgenden Aufgaben ein paar Dateien mit verschiedenen Größen. Dazu legen wir drei "Dummy-Dateien" an, die leer sind, aber eine gewisse Menge Speicher belegen. Legen Sie hierfür unter `/home/pi` einen Ordner mit dem Namen "Uebung_Speichermasseinheit" an.

Führen Sie dann die folgenden drei Befehle aus:

- `dd if=/dev/zero of=/home/pi/Uebung_Speichermasseinheit/dateiNrEins.dummy bs=1M count=5`
- `dd if=/dev/zero of=/home/pi/Uebung_Speichermasseinheit/dateiNrZwei.dummy bs=1M count=25`
- `dd if=/dev/zero of=/home/pi/Uebung_Speichermasseinheit/dateiNrDrei.dummy bs=1M count=84`

Mit diesen Befehlen haben Sie drei Dummy-Dateien angelegt. Der dd-Befehl erzeugt eine Kopie aus dem ersten Pfad (hier ein Griff in die Trickkiste) /dev/zero, welcher eine virtuelle Gerätedatei bezeichnet und eine angeforderte Anzahl Null-Bytes zurückliefert. Das bs steht für die Blockgröße, also hier 1 Megabyte und count steht für die Anzahl der Blöcke, die erstellt werden sollen.

Nach Bearbeitung der Aufgaben können Sie die drei Dateien wieder löschen.

**Aufgabe 1**

Lassen Sie sich in Ihrer Linux-Kommandozeile Ihre Daten mit den folgenden Befehlen anzeigen:

- `df -h`
- `df --si`

Welchen Unterschied stellen Sie fest?

**Aufgabe 2**

Wechseln Sie in das zuvor vorbereitete Verzeichnis `/home/pi/Uebung_Speichermasseinheit`. Lassen Sie sich die Dateien mit den folgenden Befehlen anzeigen:

- `ls -lh`
- `ls -l --si`

Welche Unterschiede können Sie nun hinsichtlich der Dateigröße erkennen? Rechnen Sie doch einmal nach.

## Podcastempfehlungen

## Zusatzmaterial

## Lernstrategien & Werkzeuge

## GitHub

### GitHub.io - LF2-Kurs als MkDocs-Variante

[https://herr-nm.github.io/MMBbS_FISI_LF02/](https://herr-nm.github.io/MMBbS_FISI_LF02/)

{%
   include-markdown "inhalte/lizenzhinweis.md"
   start="<!--Lizenzhinweis-->"
   end="<!--Lizenzhinweis-->"
%}