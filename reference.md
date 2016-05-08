Kleine Git-Referenz
===================

Git ist ein distributiertes Version Control System (VCS). Man speichert die zu
versionierenden Dateien in einem *Repository*. Jede Repo eines Projekts ist
gleichwertig. Git ist eine Sammlung von in C geschriebenen Kommandozeilenprogrammen. 

Konfiguration, Initialisierung
------------------------------

	git init

Initialisiert leeres Repository (legt `.git`-Ordner an)

	git config --global user.name "My Name"

Setzt den Namen des Users für diese Repo bzw. für diesen Benutzer, falls `--global`
verwendet wird. GitHub ignoriert diesen Namen.

	git config --global user.email "foo@bar.com"

Setzt die E-Mail-Adresse des Users. GitHub verwendet allein diese Adresse zur Identifikation.

	git config --global http.proxy "https://username:password@proxy:port"

Setzt den Proxy. Das Passwort auf dem Proxy muss angegeben werden.
Der Proxy des CSG hat die interne Adresse 10.189.1.17, Port 8000,
die Logindaten sind die, die man beim Windows-Login eingibt.

	git config --global credential.helper wincred

Nachdem der *Credential Helper* gesetzt ist, muss man sein GitHub-Passwort nicht
jedesmal eingeben.

Status und Geschichte
---------------------

	git status

Gibt Informationen zur Repo aus: nicht getrackte Dateien, geänderte Dateien,
Dateien im [Index](#glossar).

	git log

Gibt die Commit-History der ganzen Repo oder der angegebenen Dateien aus.

	git log -p

Gibt die Commit-History inklusive aller [Diffs/Patches](#glossar) zwischen den Versionen aus.

	git diff commit1 commit2

Gibt die Änderungen zwischen den beiden [Commits](#glossar) aus.

	git diff

Gibt die Änderungen zwischen dem [Working Tree](#glossar) und dem Index aus.

	git show HEAD

Zeigt die Änderungen im letzten Commit ([`HEAD`](#glossar)).

	gitk

Stellt die Commit-History graphisch dar (fancy GUI-Programm).

Änderungen protokollieren
-------------------------

	git add

Fügt angegebene Dateien in den [Index](#glossar) ein.

	git commit [-m "commit message"]

Macht die Dateien im [Index](#glossar) zu einem [Commit](#glossar).

	git commit --amend

Erlaubt eine Änderung des letzten [Commits](#glossar), falls man gederpt hat.

	git commit --amend --reset-author

Setzt den Autor des letzten [Commits](#glossar) zu den neu eingetragenen Namen.

Änderungen rückgängig machen
----------------------------

	git reset

Verwirft alle Änderungen im [Index](#glossar). Der [Working Tree](#glossar) wird nicht angetastet.

	git reset --hard HEAD

Verwirft alle Änderungen im Index und im Working Tree seit dem letzten [Commit](#glossar).

	git checkout -- <datei> <datei> ...

Verwirft alle Änderungen an den genannten Dateien seit dem letzten Commit.

	git revert [commit]

Erstellt einen neuen Commit, der die Änderungen des genannten wieder rückgängig macht
(sozusagen ein Anti-Commit).

Branching
---------

	git branch

Zeigt eine Liste aller [Branches](#glossar).

	git branch <branchname>

Erzeugt einen Branch mit diesem Namen.

	git checkout <branchname>

Wechselt zum Branch dieses Namens.

	git merge <branchname>

Merget die Branch dieses Namens mit dem aktuellen Branch.

Pushing, Fetching, Pulling, Cloning
-----------------------------------

	git clone https://github.com/USERNAME/REPO.git

Clonet die Repo, d.h. kopiert sie in ein Verzeichnis mit dem Namen der Repo.
Dann hat man sie lokal. Sie ist vollkommen gleichwertig zum Original.

	git remote -v

Listet alle [Remote Tracking Branches](#glossar) auf.

	git remote add origin https://github.com/USERNAME/REPO.git

Erstellt eine Remote Tracking Branch mit dem Namen "origin" (üblicher Name
für die Repo, die man im Internet hat).

	git push [origin] [branch]

Schickt die lokalen Commits in der Branch (Default: `master`) zum `origin`.

	git pull [origin] [branch]

Holt die Änderungen an der Repo im Netz wieder in die lokale Repo.
Eigentlich eine Kurzschreibweise für `git fetch; git merge FETCH_HEAD`.

	git fetch

Updatet alle [Remote Tracking Branches](#glossar). Braucht man meistens nicht,
man sollte lieber `git pull` verwenden.

Misc
----

Auch hilfreich: Tags, Stashing, Rebasing

.gitignore
----------

Datei, in die man einträgt, welche Dateien nicht eingefügt werden sollen
(z.B. temporäre Dateien, Dateien mit sensitiven Informationen).

Format:

	# Dies ist ein Kommentar.
	# Die folgende Zeile weist Git an, alle Dateien dieses Musters zu ignorieren.
	*.bak

	# Man kann ganze Ordnerstrukturen ignorieren.
	bin/


Glossar
=======

	Branch       unabhängiger "Ast" von Commits
	Commit       Sammlung von Änderungen im Vergleich zum letzten Commit
	Checkout     Zu einem anderen Branch wechseln
	Diff         Änderung (difference)
	Hash         Alle Objekte in Git haben einen eindeutigen SHA-1-Hash
	HEAD         neuester Commit
	Index        Enthält alle Dateien, die beim nächsten Commit committet werden
	Master       standardmäßiger Name des Hauptbranches
	Patch        Synonym zu Diff
	Remote Tracking Branch
	             Branch, der auf einen Branch auf einem anderen System zeigt (z.B. github.com)
	Repository   Ort, der das Projekt enthält
	SCM          Source Code Management, häufig als Synonym zu VCS
	Staging      Aufnahme einer Datei in den Index
	Tag          "Zeiger" auf einen Commit, z.B. zum Markieren einer Version (v1.4)
	Trunk        Synonym zu Master in anderen VCS
	VCS          Version Control System
	Working Tree Arbeitsverzeichnis
