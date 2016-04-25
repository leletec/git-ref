# Markdown-Testdatei
====================

Überschriften:
------------------
# Das ist eine Überschrift
## Das ist eine Überschrift
###### Das ist eine Überschrift

Betonungen
---------------
*Dieser Text ist kursiv gedruckt.*   _Dieser auch._

**Dieser Text ist fett gedruckt.**   __Dieser auch.__

~~Dieser Text wird durchgestrichen.~~   <del>Dieser auch.</del>

*Die ~~beiden~~ drei Möglichkeiten __können__ auch kombiniert werden*

Listen:
---------
1. Ungeordnet:
    * mit *
    * mit -
        - etc
        - ...
2. Geordnet: mit Nummern
		
Links:
--------
http://github.com/okitec - automatisch generiert

[Meine Seite auf GitHub](http://github.com/leletec)
		
Zitate:
--------
Wie schon viele weise Menschen sagten:
> Zitate

> sind toll.
		
Code:
-------
An dieser Stelle könnte man auch etwas `code` schreiben!

```batch
@echo off
title Das ist eine Batch Datei

set /P lieblingsfrucht="Was ist Ihre Lieblingsfrucht? "
if %lieblingsfrucht%==Banane goto richtig
exit

:richtig
echo Hurra, Sie haben Recht!
pause >nul
```

    public class foo() {
      private boolean statement;
      public void foobar() {
        statement = false;
      }
    }


Task Lists:
-------------
- [x] @mention, **Formatierungen** etc wird hier unterstützt.
- [x] Man braucht irgendeine Form von Listen-Syntax.
- [x] Das ist erledigt.
- [ ] Das nicht.

Tabellen:
-----------
Spalte 1 | Spalte 2 | Banane
---------- | ----------- | ---------
Inhalt Spalte 1 | Inhalt Spalte 2 
foo | bar | .
w | t | f 

Emojis:
---------
Ja, die werden auch unterstützt :+1: :smile:
