Plone-Theme
===========

``zchl.basetheme`` basiert auf `vs.basetheme <https://github.com/veit/vs.basetheme>`_.

Installation
------------

In der ``devel.cfg``-Datei wird nun das Theme registriert mit::

    [buildout]
    …
    develop =
        …
        src/zchl.basetheme

    [instance-base]
    eggs +=
        …
        zchl.basetheme

Das Theme wird automatisch mit ``zchl.policy`` mitinstalliert da in ``zchl.policy/src/zchl/policy/profiles/default/metadata.xml`` folgendes eingetragen wurde::

    <dependencies>
        <dependency>profile-zchl.basetheme:default</dependency>
    </dependencies>

Aufbau
------

Das Theme-Produkt hat folgende Struktur::

    |-- CHANGES.rst
    |-- CONTRIBUTORS.rst
    |-- README.rst
    |-- bootstrap.py
    |-- docs
    |   |-- LICENSE.GPL
    |   `-- LICENSE.txt
    |-- setup.cfg
    |-- setup.py
    `-- src
        |-- zchl
    	|-- __init__.py
    	`-- basetheme
    	    |-- __init__.py
    	    |-- configure.zcml
    	    |-- profiles
    	    |   `-- default
    	    |       |-- metadata.xml
    	    |       `-- registry.xml
    	    |-- static
    	    |   |-- css
    	    |   |   |-- IEFixes.css
    	    |   |   |-- main.css
    	    |   |   `-- min.css
    	    |   |-- images
    	    |   |   |-- album.png
    	    |   |   |-- favicon.ico
    	    |   |   |-- logo.jpg
    	    |   |   |-- logo.png
    	    |   |   |-- pb_close.png
    	    |   |   |-- treeCollapsed.png
    	    |   |   `-- treeExpanded.png
    	    |   |-- index.html
    	    |   |-- manifest.cfg
    	    |   `-- rules.xml
    	    |-- testing.py
    	    `-- tests
    	|-- __init__.py
    	`-- test_example.py

Dabei wid in der ``configure.zcml``-Datei der ``static``-Ordner konfiguriert::

 <configure
     …
     xmlns:plone="http://namespaces.plone.org/plone">

   <plone:static
         directory="static"
         type="theme"
         />

In diesem ``static``-Ordner befindet sich dann das eigentliche Theme, das im
Wesentlichen aus folgenden Dateien besteht:

``images``
    In diesem Ordner liegen die Bilder, die durch main.css referenziert werden.

``index.html``
    Enhält die grundlegende HTML-Struktur der Seite.

``manifest.cfg``
    Enthält die Definition der Eigenschaften und Parameter des Theme.

``rules.xml``
    Enthält die Diazo-Transformationsregeln, weiter Infos hier:
    `Diazo BASIC SYNTAX <http://docs.diazo.org/en/latest/basic.html>`_
    Diese Diazo-Regeln werden in Plone verfügbar durch plone.app.theming.
