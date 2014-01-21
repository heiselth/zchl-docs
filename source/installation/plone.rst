Plone
=====

Buildout-Projekt erstellen
--------------------------

* Verzeichnis plone43_buildout erstellen
* in dieses Verzeichnis bootstrap.py kopieren (von http://downloads.buildout.org/2/bootstrap.py)
* datei base.cfg erstellen (von: https://github.com/veit/vs_buildout)

``[buildout]``
    Zentraler Abschnitt einer Buildout-Konfiguration
``parts``
    bestimmt, welche Abschnitte und in welcher Reihenfolge diese Abschnitte assgefuehrt werden.
``find-links``
    erlaubt die Angabe von URLs zu Listen von Paketquellen
``socket-timeout``
    Angabe, wann ein Timeout angezeigt werden soll. Um zum frümöchen Zeitpunkt diese Meldung zu erhalten, wird die Zeit auf drei Sekunden verkuerst.
``extensions``
    Liste von Erweiterungen füldout
``allow-picked-versions``
    erlaubt in Produktivumgebungen, nicht-festgeschriebene Versionen zu verbieten
``show-picked-versions``
    erlaubt in Testumgebungen sich die nicht-festgeschriebenen Module und ihre Versionen anzeigen zu lassen.
``versions``
    gibt den Namen des Abschnitts an, in dem die Pakete mit bestimmten Versionsnummern angegeben werden koennen
``unzip``
    wenn der Wert ``true`` ist, werden gezippte Pakete auch von Buildout ausgepackt
``develop``
    Liste von Pfaden zu Python-Modulen, die sich in der Entwicklung befinden

``plone.recipe.zope2instance``
    Weitere Informationen zu diesem Rezept finden Sie in https://pypi.python.org/pypi/plone.recipe.zope2instance

``zopepy``
    Python-Interpreter, der alle Module der Instanz bereits importiert hat


Wechsel in Python2.7.6
neues VRZ Extensions
Wechsel nach Extensions
Install von easy_install
Download: wget peak.telecommunity.com/dist/ez_setup.py
/opt/python/2.7.6/bin/python/ez_setup.py
ploneuser add -m plone
su - plone
mkdir plone43_buildout
Wechsel in dir
Download: wget download.buildout.org/2/bootstrap.py
base.cfg anlegen in plone43_buildout  (quelle: github veit schiele)
rechte äern auf plone user
bash.rc konfigurieren: export PATH=/opt/python/2.7.6/bin:$PATH
source .bash.rc
which python zur kontrolle
Wechsel zu plone43_buildout
python bootstrap.py -c devel.cfg
versionskonflikt bei setuptools, brauchen grö 0.7
Wechsel zu su
/opt/python/2.7.6/bin/python/easy_install setuptools==0.9.8
Wechsel zu user plone
Wechsel zu plone43_buildout
python bootstrap.py -c devel.cfg
builout script wird erstellt
/bin/buildout -c devel.cfg  (baut zope plone mit allen modulen)
werden pakete nachinstalliert muss python neu installiert werden
buildout muss danach wieder neu erstellt werden
su
zchl.policy nach /plone43_buildout/src kopieren
su - Plane
/plone43_buildout/bin/buildout -c devel.cfg
./bin/instanz
