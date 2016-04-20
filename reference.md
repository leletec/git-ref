Kleine Git-Referenz
===================

Git ist ein distributiertes Version Control System (VCS). Man speichert die zu
versionierenden Dateien in einem *Repository*. Jede Repo eines Projekts ist
gleichwertig. Git ist eine Sammlung von in C geschriebenen Kommandozeilenprogrammen. 

	git init
	           Initialisiert leeres Repository (legt `.git`-Ordner an)
	git add
	           Fügt angegebene Dateien in den *Index* ein.
	git commit [-m "commit message"]
	           Macht die Dateien im *Index* zu einem *Commit*.
	git commit --amend
	           Erlaubt eine Änderung des letzten Commits, falls man gederpt hat.
	git status
	           Gibt Informationen zur Repo aus: nicht getrackte Dateien,
	           geänderte Dateien, Dateien im Index.
	git config [--global] user.name "My Name"
	           Setzt den Namen des Users für diese Repo bzw. computerweit,
	           falls `--global` verwendet wird. GitHub ignoriert diesen Namen.
	git config [--global] user.email "foo@bar.com"
	           Setzt die E-Mail-Adresse des Users. GitHub verwendet allein
	           diese Adresse zur Identifikation.
	git config --global http.proxy "https://username:password@proxy:port"
	           Setzt den Proxy. Das Passwort auf dem Proxy muss angegeben werden.
	           Der Proxy des CSG hat die interne Adresse 10.189.1.17, Port 8000.
	git commit --amend --reset-author
	           Setzt den Autor des letzten Commits zu den neu eingetragenen
	           Namen.
	git log
	           Gibt die Commit-History der ganzen Repo oder der angegebenen
	           Dateien aus.
	git log -p
	           Gibt die Commit-History inklusive aller Diffs/Patches zwischen
	           den Versionen aus.
	git diff commit1 commit2
	           Gibt die Änderungen zwischen den beiden Commits aus.
	git diff
	           Gibt die Änderungen zwischen dem Index und dem neuesten Commit aus.
	gitk
	           Stellt die Commit-History graphisch dar.
	git branch
	           Zeigt eine Liste aller Branches.
	git branch <branchname>
	           Erzeugt einen Branch mit diesem Namen.
	git checkout <branchname>
	           Wechselt zum Branch dieses Namens.
	git reset
	           Verwirft alle Änderungen im Index. Der Working Tree wird nicht
	           angetastet.
	git reset --hard HEAD
	           Verwirft alle Änderungen im Index und im Working Tree seit dem
	           letzten Commit.
	git merge <branchname>
	           Merget die Branch dieses Namens mit dem aktuellen Branch.

Glossar
=======

	Index        Enthält alle Dateien, die beim nächsten Commit committet werden.
	Working Tree Das normale Arbeitsverzeichnis