t3update.sh
===========

Dieses Script ist für ein semi-automatisches Update von TYPO3 Installationen bei [domainFACTORY](http://www.df.eu), insbesondere dem Reseller Tool RP gedacht. Hauptanwendungsbereich ist die Installation von Bugfix Releases von [TYPO3](http://typo3.org). Ursprünglich wurde das Skript im [domainFACTORY Kundenforum](https://www.df.eu/forum/threads/51430-Shell-Script-f%C3%BCr-Updates-von-TYPO3-Installationen-bei-df) veröffentlich. Dort ist auch jederzeit Feedback möglich.

Funktionen aus dem Install Tool, z.B. das setzen von [SYS][compat_version] oder ein compare im Database Analyzer werden durch das Script NICHT übernommen!

**Achtung: Aktuell unterstützt das Skript nur TYPO3 4.5 LTS. Eine Anpassung an aktuelle TYPO3 Versionen ist aber geplant!**

Was macht das Script genau?
- Runterladen des gewünschten Source von typo3.org
- entpacken des Source
- Source Tarball wieder löschen
- .htaccess Dateien für mod_expires durch umbennnen aktivieren
- alten Symlink im Dummy Verzeichnis löschen
- neuen Symlink anlegen
- index.php aus Source Verzeichnis in Dummy Verzeichnis kopieren
- neuen Encryption Key generieren
- Cache Tabellen in der Datenbank leeren
- temp\_CACHED\_* Dateien aus /typo3conf löschen

**Die Nutzung dieses Scripts erfolgt auf eigene Gefahr! Vor jedem Update sind Backups anzufertigen!**

Teile dieses Scripts wurden dem [TYPO3 mass upgrade script](http://www.typofree.org/article/archive/2009/january/title/typo3-mass-upgrade-script/) von Michiel Roos entnommen oder dadurch inspiriert.

Installation & Nutzung
----------------------

Voraussetzung ist eine Symlink Installation von TYPO3 und ein SSH Zugang. Per Default wird davon ausgegangen, dass der TYPO3 Source in der Regel immer in einem Unterverzeichnis des in der Variablen SRC\_DIR bezeichneten Verzeichnisses gespeichert ist.
Desweiteren wird davon ausgegangen, dass sich dieses Shell Script im Ordner oberhalb des Document Roots befindet. Das Dummy Verzeichnis lässt sich über die Variable DUMMY_DIR anpassen.
Über die Variablen lässt sich das Script leicht an eigene Bedürfnisse anpassen.

Das Script muss in jede RP Instanz kopiert werden, da bei domainFACTORY kein zentraler Zugriff auf alle TYPO3 Instanzen möglich ist.

Um das Script nutzen zu können muss es ausführbar gemacht werden:

    chmod +x t3update.sh

Aufruf des Scripts:

    ./t3update.sh

Im Script gibt es ein paar Yes/No Entscheidungen. Der jeweilige Default Wert ist durch einen Grossbuchstaben sichtbar, z.B. Y/n
In diesem Fall entspricht ein Enter dem Y und man kann sich die Eingabe sparen.