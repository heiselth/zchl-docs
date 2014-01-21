Sphinx
======


in /home/plone Vrz. zchl-docs anlegen
bootstrap.py holen wie oben
buildout Datei erstellen

[buildout]
parts =
    sphinxbuilder

[sphinxbuilder]
recipe = collective.recipe.sphinxbuilder
outputs = html
source = ${buildout:directory}/source
build = ${buildout:directory}/docs
eggs =
    Sphinx
    docutils
    roman
    Pygments

[versions]
collective.recipe.sphinxbuilder = 0.7.0
docutils = 0.8.1
Jinja2 = 2.6
Pygments = 1.5
roman = 1.4.0
Sphinx = 1.1.3
zc.recipe.egg = 1.3.2


python bootstrap.py
./bin/buildout
in docs symbolischen link ln -s /srv/www/htdocs/ html
./bin/sphinx/sphinxbuilder
in source/www/htdocs wird die Dokumentation erzeugt
Aufruf üpache
im source Vrz gibt es eine config.py
dort kann die Version geäert werden, der projektname, Sprache
