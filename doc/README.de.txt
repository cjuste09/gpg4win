;; README.de.txt                             -*- coding: latin-1; -*-
;; This is the README installed with Gpg4win (German version).  Lines
;; with a ; in the first column are considered a comment and not
;; included in the actually installed version.  Certain keywords are
;; replaced by the Makefile; those words are enclosed by exclamation
;; marks.

                  Deutsche README Datei f�r Gpg4win
                  =================================

Dies ist Gpg4win, Version !VERSION! (!BUILD_ISODATE!).

Inhalt:

     1. Wichtige Hinweise
     2. �nderungen
     3. Anmerkungen
     4. Versionsgeschichte
     5. Versionsnummern der einzelnen Programmteile
     6. Rechtliche Hinweise


1. Wichtige Hinweise
====================

Hilfe bei der Installation und Benutzung von Gpg4win bietet Ihnen das
Gpg4win-Kompendium. Sie finden es nach der Installation
auf Ihrem System (wo genau, ist abh�ngig von Ihrer Windows-Version)
oder online auf
    https://www.gpg4win.de/documentation-de.html

Bitte lesen Sie den Abschnitt "3. Anmerkungen" dieses READMEs,
bevor Sie Gpg4win nutzen.

Im Kompendium finden Sie weitere Hinweise zur manuellen oder automatischen
Installation.


Systemvoraussetzungen
---------------------

Gpg4win l�uft auf Windows Versionen 7 oder neuer (bis Windows 10).
32- und 64bit-Systeme werden unterst�tzt. Wird mindestens Windows XP verwendet,
k�nnen einige Komponenten von Gpg4win verwendet werden, sie sind allerdings
nicht offiziell unterst�tzt.

Das Outlook-Plugin GpgOL ist kompatibel mit Microsoft Outlook 2010, 2013 und
2016 (sowohl 32 als auch 64bit) und unterst�tzt E-Mail Transport per SMTP/IMAP
und MS Exchange Server (ab Version 2010). F�r die alten Outlook-Versionen
2003 und 2007 wird eine reduzierte Menge an Funktionen angeboten.

(Aktuellste Angaben auf https://www.gpg4win.de/system-requirements-de.html .)



2. �nderungen
=============

Die integrierten Gpg4win-Komponenten in Version !VERSION! sind:

!COMPONENTS!


Neu in Gpg4win Version !VERSION! (!BUILD_ISODATE!)
-----------------------------------------

- GnuPG: Zwei Probleme wurden behoben welche zu einer
  Blockade des GnuPG Systems f�hren konnten. (T3378)

- GpgOL: Weitere augenscheinlich zuf�llige Abst�rze von Outlook
  wurden beseitigt. (T3484)

- GpgOL: Outlook wird nicht mehr blockiert wenn viele Mails
  gleichzeitig ausgew�hlt werden. (T3433)

- GpgOL: Konten die mit dem G Suite Sync Plugin eingerichtet wurden
  werden nun erkannt. Mit diesen Konten werden bisher nur
  reine ("No-MIME") verschl�sselte PGP Textnachrichten, ohne
  Anh�nge, unterst�tzt.
  Das senden von signierten Nachrichten wird nicht unterst�tzt.
  Lesen von Krypto Mails ist vollst�ndig unterst�tzt. (T3545)

- GpgOL: Die Option "No-MIME" verschl�sselte,
  unsignierte Textnachrichten, ohne Anh�nge zu versenden funktioniert
  wieder (T3514)

- GpgOL: Die Verarbeitung und Fehlerbehandlung von signierten,
  unverschl�sselten Mails wurde verbessert.

- GpgOL: Verschiedene Geschwindigkeits- und
  Leistungs-Verbesserungen.

- GpgOL: Verbesserte Erkennung von gro�en PGP/MIME Nachrichten und
  MS-TNEF Nachrichten. (T3419 , T3542)

- Kleopatra: Das Passwort Eingabefeld �ffnet sich nicht mehr
  teilweise im Hintergrund. (T3460)

- Kleopatra: Das entschl�sseln von Archiven �ber Partitionsgrenzen
  hinweg funktioniert nun. (T3547)

- Kleopatra: Ein m�glicher Absturz in der GpgOL Zertifikatsauswahl
  wurde behoben. (T3544)

- Kleopatra: Die Vorauswahl von verschl�sseln / signieren mit GpgEX
  funktioniert erneut. (T3543)

- Kleopatra: Web Key Directories werden nun bei der
  Dateiverschl�sselung unterst�tzt. (T3548)

- Kleopatra: Ein Absturz bei der Schl�sselsuche auf einem LDAP
  Schl�sselserver wurde behoben. (T3550)

- Kleopatra: Ein Absturz wenn die Schl�sselerstellung abgebrochen
  wurde ist behoben. (T3577)

- Kleopatra: Beglaubigungen k�nnen nun wieder aus den Zertifikatsdetails
  heraus angezeigt werden. (T3579)

- Kleopatra: Es ist nun m�glich Zertifikate �ffentlich zu beglaubigen
  auch wenn dieses bereits lokal signiert wurde. (T1649)


3. Anmerkungen
==============

- GpgOL

  * Es ist nicht m�glich E-Mails zu ver�ndern (z.B. sie zu verschieben oder
    Flaggen zu setzen) w�hrend diese entschl�sselt betrachtet werden.
    Um dies zu umgehen schlie�en Sie die entsprechende Mail oder w�hlen
    Sie ab und modifzieren / verschieben diese dann �ber Rechtsklick oder
    Drag & Drop.

  * Crypto E-Mails, die als Anhang weitergeleitet wurden,
    werden nicht verarbeitet.

  * Der Zertifikatsauswahldialog �ffnet sich teilweise im Hintergrund
    und bedarf insgesamt einer �berarbeitung.

  * Als weitere Sprachen sind nur Englisch und Portugisisch verf�gbar.

- Allgemein

  * F�r Version 3.1 planen wir eine einfache M�glichkeit, in einen
    automatisierten Modus zu wechseln. Dies w�rde die folgenden GnuPG-Optionen
    setzen:

        auto-key-locate wkd
        auto-key-retrieve
        trust-model tofu+pgp

    Da das neue Vertrauensmodell noch nicht vollst�ndig in Kleopatra behandelt
    wird (insbesondere bez�glich Dateisignaturen), sind diese Optionen noch
    nicht voreingestellt.

    Sie k�nnen sie jedoch manuell in der gpg.conf setzen. Das neue
    Vertrauensmodell wird von GpgOL bereits unterst�tzt.

- GpgOL f�r Outlook 2003 und 2007

  Die Unterst�tzung von Outlook 2003 und 2007 ist veraltet
  und wird in einer zuk�nftigen Version vollst�ndig entfernt werden.

  * Nur f�r Outlook 2003/2007:
    Sie sollten unbedingt vor der Installation von GpgOL
    Sicherheitskopien Ihrer alten verschl�sselten/signierten E-Mails
    erstellen, z.B. in PST-Dateien!

  * Nur f�r Outlook 2003/2007:
    Senden von signierten oder verschl�sselten Nachrichten �ber ein
    Exchange-basiertes Konto funktioniert nicht.
    (Hinweis: Beim Verwenden von SMTP sollte das Senden
     mit GpgOL funktionieren. Oder Sie nutzen GpgOL mit Outlook
    2010 oder neuer.)

  * Nur f�r Outlook 2003/2007:
    Verschl�sselte E-Mails unverschl�sselt auf E-Mail-Server:
    Es kann vorkommen, dass Teile von verschl�sselten E-Mails
    in entschl�sselter/unverschl�sselter Form auf dem E-Mail-Server
    (IMAP oder MAPI) zu liegen kommen, wenn man sie erstellt/liest.
    Betroffen sind nur der Inhalt des Anzeigefensters von Outlook,
    also der "E-Mail-Body". Anh�nge sind nicht betroffen.
    Schaltet man die Voransicht von Outlook ab, so
    verringert sich die Wahrscheinlichkeit daf�r deutlich,
    aber es kann trotzdem noch passieren. (Wenn Ihnen das Sorge bereitet:
    nutzen Sie GpgOl mit Outlook 2010 oder neuer.)


4. Versionsgeschichte
=====================

Eine aktuelle, deutschsprachige �bersicht der �nderungen finden Sie online
unter: https://www.gpg4win.de/change-history-de.html
Im Weiteren finden Sie die Eintr�ge aus der englischen NEWS-Datei:

!NEWSFILE!


5. Versionsnummern der einzelnen Programmteile
==============================================

Zur �bersicht sind hier die Pr�fsummen, sowie die Namen der einzelnen
Bestandteile, aufgelistet.

!VERSIONINFO!


6. Rechtliche Hinweise zu den einzelnen Bestandteilen der Software
==================================================================

Gpg4win besteht aus einer ganzen Reihe von unabh�ngig entwickelten
Paketen, die teilweise unterschiedliche Lizenzen haben. Der Gro�teil
dieser Software ist, wie Gpg4win selbst, kompatibel mit der GNU General
Public License (GNU GPL). Allen gemeinsam ist, dass es Freie Software ist,
welche ohne Restriktionen benutzt werden kann, studiert und ver�ndert werden
darf, sowie, dass �nderungen weitergeben d�rfen. Wenn die Quelltexte (also
gpg4win-x.y.z.tar.bz2) mit weitergegeben werden und auf die die GNU
GPL hingewiesen wird, ist die Weitergabe fast immer m�glich.

Zur �bersicht folgt eine Liste der Copyright Erkl�rungen.


!PKG-COPYRIGHT!


*** Ende der Datei ***
