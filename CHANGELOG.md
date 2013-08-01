Changelog
=========

### 0.4.3 (31.01.2011)
* [Bugfix] wget Befehl modifiziert um *?download* Parameter zu entfernen
* [Change] Modifikation der Datei typo3/cli_dispatch.phpsh entfernt. Skript stattdessen wie folgt aufrufen:
	`/bin/env -i /usr/local/bin/php5 -f /pfad/zu/typo3/cli_dispatch.phpsh scheduler`

### 0.4.2 (19.08.2010)
* [Bugfix] .htaccess Prüfung überarbeitet
* [Bugfix] Umlaute ersetzt wegen fehlerhafter Darstellung unter Mac OS X

### 0.4.1 (19.04.2010)
* [Bugfix] Falsches Source Verzeichnis, wenn SRC_DIR neu gesetzt wurde (Danke an Stefan Busemann)
* Kleine Verbesserungen, wenn Pfade neu gesetzt werden

### 0.4 (09.04.2010)
* Prüfung, ob die .htaccess Dateien für mod_expires bereits aktiviert sind (das ist seit TYPO3 4.3 standardmässig der Fall)
* Generierung eines neuen Encryption Keys, da viele Installationen immer noch einen schwachen Key verwenden
* Cache Tabellen in der Datenbank leeren
* Pfad zu PHP in cli_dispatch.phpsh ändern
* Code Cleanup und mehr Kommentare

### 0.3 (09.02.2009)
* Prüfung, ob Source Download erfolgreich war
* index.php aus Source Verzeichnis in Dummy Verzeichnis kopieren

### 0.2 (21.01.2009)
* erste öffentliche Version
* Finetuning
* temp_CACHED_ Dateien aus typo3conf löschen
* weitere erklärende Texte im Script Header

### 0.1 (21.01.2009)
* Erste funktionierende Version