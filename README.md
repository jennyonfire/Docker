# M300 - Dokumentation von Jennifer Fischer, Jan Gantenbein &amp; Dennis Allenspach
Im Modul 300 wurde uns die Arbeit mit Containers und Virtuellen Maschienen näher gebracht.
## Auftrag LB2
In der LB2 ging es darum einen Dienst mit Docker zur Verfügung zu stellen.
## Bewertung
* Umgebung (funktionsfähig auf eigenem Notebook (Note 4.0)
* Bestehende Docker Container kombieren oder Container als Backend, Desktop App als Frontend (Note 4.5)
* Eigene Container erstellen (Note 5.0 – 5.5)
* Projekt auf github Ablegen und Dokumentieren (Markdown) (Note 5.5 – 6.0)

## Beschrieb des Service
Unser Service besteht aus 3 verknüpften Container. Einem Wordpress, MySQL und PHPMyAdmin Server. Der Service soll die Erstellung einer Webumgebung ersparen bzw. vereinfachen. Die 3 Services wurden mit einem Docker-Compose file kreeiert und wird mittels vagrantfile ausgeführt. Die Services besitzen natrülich ein stetiges Volume welches erhalten bleibt.

## Technische Angaben inkl. Plan und Anleitung für den Betrieb

**Netzwerkplan:**

![Netzwerkplan_Docker](https://github.com/Dionysos376/Docker/blob/master/Netzwerkplan_Docker.png)

_Gelb = Netzwerk Zone der 3 Containers_

**Betrieb**
Schritt 1 ist natrülich das Git Repository auf den lokalen Host zu kopieren. (Via git Clone oder als .zip)

Um die Dienste erfolgreich benutzen zu können, sollte man im Vagrant File die IP der VM nach Wunsch ändern. (Möglicherweise auf Bridge umstellen). Danach sollte man im Docker-Compose File den Benutzernamen, Passwort und Rootpasswort für die Datenbank ab ändern. Beachtet muss werden, dass die Änderung im Wordpress Service nachgetragen werden muss.

DB Standardname und Passwort sind: <br>
  - Name = dbuser <br>
  - Passwort = Hallo1234

Linux ubuntu Standardname und Passwort sind: <br>
  - Name = vagrant <br>
  - Passwort = vagrant

Finaler Schritt ist es mit einer Konsole wie Git Bash. Im Repository Verzeichnis, den Befehl vagrant up auszuführen.
Die Installation dauert eine Weile und anschliessend können die Dienste wie folgt erreicht werden:

Wordpress Seite anzeigen: http://ip_des_Computers:8000 <br>
(Bei der ersten Öffnung muss noch die Erstinstallation vorgenommen werden. Name, Passwort, E-Mail und Websitenamen eintragen) <br>
Wordpress Admin Account: http://ip_des_Computers:8000/wp-admin <br>
PHPMyAdmin Interface: http://ip_des_Computers:8080 (Username und Passwort welche man vorhin geändert hat. <br>
## Testing
Getestet können die Dienste folgendermassen: <br>
Auf Webinterfaces Zugreifen <br>
Datenbank User erstellen, löschen. Container neustartetn, DB kontrollieren ob die Dateien immernoch vorhanden sind. 
## Troubleshooting Stepps (optional)
Mögliche Probleme können entstehen: <br>
  - Netzwerk (Kontrollieren sie wie die Netzwerkkonfiguration ist. <br>
  - Versions Probleme (Bei neueren Versionen gibt es möglicherweise Änderungen welche diese Konfiguration nicht mehr ermöglichen)
