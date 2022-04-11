Linux-Kommandos für DevOps und Netzwerke [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
===============
<hr>
<p align="center">
	<img alt="Git" src="../Img/linux.svg" height="190" width="455">
</p>
<hr>

### Index

* [lsof Kommando](#lsof_kommando)
* [Gruppen und Benutzer](#gruppen_und_benutzer)
* [id Kommando](#id_kommando)
* [cat Kommando](#cat_kommando)
* [diff Kommando](#diff_kommando)
* [dd Kommando](#dd_kommando)
* [route Kommando](#route_kommando)
* [mtr Kommando](#mtr_kommando)
* [nslookup ve dig Kommandos](#nslookup_ve_dig_kommandos)
* [tcpdump Kommando](#tcpdump_kommando)
* [sudo !! Kommando](#sudo_!!_kommando)
* [wget Kommando](#wget_kommando)
* [free Kommando](#free_kommando)
* [tr Kommando](#tr_kommando)
* [htop, ps ve kill Kommandos](#htop_ps_ve_kill_kommandos)
* [head and tail Kommandos](#head_and_tail_kommandos)
* [man Kommando](#man_kommando)
* [sort Kommando](#sort_kommando)
* [chown Kommando](#chown_kommando)
* [chmod Kommando](#chmod_kommando)

<hr>

## lsof Kommando 
##### (lsof(List Of Open File) listet alle laufenden Dateien auf dem System auf)

##### Listet Dateien auf, die vom angegebenen Benutzer geöffnet wurden:
```
lsof -u “Benutzer”
```

<hr>

## Gruppen und Benutzer

##### Fügt einen neuen Benutzer hinzu:
```
sudo useradd “Nutzername”
```

##### Erstellt das Passwort des neuen Benutzers:
```
sudo passwd “Nutzername” 
```

##### Löscht den angegebenen Benutzer:
```
sudo userdel “Nutzername” 
```

##### Erstellt eine neue Gruppe:
```
sudo groupadd “Gruppenname” 
```

##### Löscht die angegebene Gruppe:
```
sudo groupdel “Gruppenname” 
```

##### Fügt den angegebenen Benutzer der angegebenen Gruppe hinzu:
```
sudo usermod -g “Gruppenname” “Nutzername” 
```

<hr>

## id Kommando
##### (Listet die numerischen IDs von Benutzern und Gruppen auf)

##### Aktuelle Gruppen-ID:
```
id -g 
```

##### IDs aller Gruppen:
```
id -G
```

##### Aktuelle Benutzer-ID:
```
id -u 
```

<hr>

## cat Kommando
##### (Mit diesem Befehl können wir Dokumente lesen, ändern und zusammenführen)

##### Kombiniert die Dokumente test-1.txt und test-2.txt und dann gibt die Ausgabe:
```
cat “test-1.txt” “test-2.txt” 
```

##### Nummeriert alle Zeilen des ausgewählten Dokuments:
```
cat -b 
```

##### Nummeriert auch die nicht leeren Zeilen des ausgewählten Dokuments:
```
cat -n 
```

<hr>

## diff Kommando

##### Dieser Befehl listet die Unterschiede zwischen den beiden Dateien auf:
```
diff “test-1.txt” “test-2.txt”
```

<hr>

## dd Kommando
##### (Dieser Befehl kopiert das angegebene Dokument oder Verzeichnis an das angegebene Ziel. Im Gegensatz zu cp kopiert es Byte-zu-Byte. Wenn Sie beispielsweise eine Festplatte auf eine andere Festplatte kopieren, wird eine exakte Kopie der Festplatte erstellt (wie ein AWS-Snapshot))

##### Kopiert Mp1-Disc auf Mp2-Disc wie sie ist:
```
dd if = /dev/mp1 of = /dev/mp2 
```

##### Sollen die Fehler beim Kopiervorgang ignoriert werden, wird der Parameter conv=noerror angegeben:
```
dd conv=noerror if = /dev/mp1 of = /dev/mp2
```

<hr>

## route Kommando

##### Listet die Routing-Tabelleninformationen des aktuellen Netzwerks auf:
```
route
```

##### Gibt an, wie viele Hops das Paket, das mit dem ICMP-Protokoll an das angegebene Ziel gesendet wurde, das Ziel erreicht:
```
traceroute google.com
```

<hr>

## mtr Kommando
##### (Der Befehl mtr kombiniert die Befehle ping und traceroute. Es listet detailliert die Datenverluste und Verzögerungszeiten im gesendeten Paket in Echtzeit auf)

##### Listen in Echtzeit:
```
mtr google.com 
```

##### Es wirft nur 10 Pakete auf das Ziel und listet das Ergebnis als Bericht auf. Der Parameter „-n“ blockiert die DNS-Auflösung:
```
mtr -n --report google.com
```

<hr>

## nslookup ve dig Kommandos

##### Sortiert die NS- und SOA-Einträge der angegebenen Adresse:
```
nslookup github.com
```
```
dig google.com
```

<hr>

## tcpdump Kommando
##### (Es fragt den Status aller Netzwerkschnittstellen auf dem Computer ab und erfasst die von den Schnittstellen gesendeten Pakete)

##### Listet alle Schnittstellen auf:
```
sudo tcpdump --list-interfaces
```

##### Hört auf Paketübertragung aller Schnittstellen:
```
sudo tcpdump
```

##### Hört auf Paketübertragung der angegebenen Schnittstelle:
```
sudo tcpdump -i eth0
```

##### Beschränkt das Abhören von Paketen auf 10:
```
sudo tcpdump -i eth0 -c 10 
```

<hr>

## sudo !! Kommando

##### Dieser Befehl wiederholt den davor auf der Kommandozeile eingegebenen Befehl mit Root-Berechtigung:
```
sudo !!
```

<hr>

## wget Kommando

##### Mit diesem Befehl wird die angegebene Webseite heruntergeladen:
```
wget https://www.linkedin.com/in/mahmut-edip-negiz-6b1145213/
```

<hr>

## free Kommando

##### Listet den Nutzungsstatus der Festplatte auf:
```
free
```

##### Listet den Festplattennutzungsstatus in Byte auf:
```
free -b
```

#####  Listet den Nutzungsstatus des Datenträgers in Kilobyte Byte auf (default):
```
free -k
```

##### Listet den Festplattennutzungsstatus in Megabyte Byte auf:
```
free -m
```

##### Listet den Festplattennutzungsstatus in Gigabyte Byte auf:
```
free -g
```

<hr>

## tr Kommando
##### (Innerhalb der mit dem tr-Befehl angegebenen Datei können Manipulationen vorgenommen werden. Rohre | Komplexere Skripte können mit geschrieben werden)

##### Alle e's in test.txt werden o sein:
```
cat test.txt | tr “e” “o” 
```

#####  Alle Kleinbuchstaben in test.txt werden GROSS geschrieben:
```
cat test.txt | tr “[a-z]” “[A-Z]”
```

#####  Alle i's in test.txt werden gelöscht:
```
cat test.txt | tr -d “i” 
```

<hr>

## htop, ps ve kill Kommandos

##### htop zeigt die CPU- und Speicherauslastung in Echtzeit an. Anders als der Befehl ps ist er interaktiv mit der Maus:
```
htop
```

#####  Der Befehl ps zeigt auch die CPU- und Speicherauslastung an, im Gegensatz zum Befehl htop meldet er die Ausgabe:
```
ps aux

a = Zeigt die Transaktionen aller Benutzer an.
u = Zeigt den Eigentümer der Aktion an.
x = Zeigt Prozesse an, die nicht mit dem Terminal verbunden sind.
```

#####  Der Prozess wird beendet, indem diese IDs mit dem Kill-Befehl verwendet werden:
```
kill “ID”
```

<hr>

## head and tail Kommandos

##### Gibt die ersten zehn Zeilen des Dokuments aus:
```
head “datei.txt” 
```

##### Extrahiert die letzten zehn Zeilen des Dokuments:
```
tail “datei.txt”  
```

<hr>

## man Kommando

##### Dieser Befehl erklärt die detaillierte Verwendung aller anderen Befehle:
```
man whoami
```

<hr>

## sort Kommando
##### (Mit diesem Befehl wird sowohl alphabetisch als auch numerisch sortiert. Sortiert Dateien, Dateiinhalte und Verzeichnisse. Groß-/Kleinschreibung wird beim Sortieren beachtet)

##### Sortiert die Ausgabe in umgekehrter Reihenfolge:
```
sort -r
```

##### Sortiert die Ausgabe ohne Berücksichtigung der Groß-/Kleinschreibung:
```
sort -f 
```

##### Sortiert die Ausgabe numerisch:
```
sort -n
```

<hr>

## chown Kommando

##### Ändert den Besitz von Dateien:
```
sudo chown “Benutzername_oder_Gruppenname” “Dateinamen”
```

<hr>

## chmod Kommando

##### Dieser Befehl wird verwendet, um die Zugriffsberechtigungen von Dateien und Verzeichnissen zu ändern. Jede Ziffer steht für Benutzer, Gruppe und andere:
```
chmod 754 “dosya.txt”

4 →read(r) permission
2 → write(w) permission
1 → execute(x) permission
0 → no permission
```
