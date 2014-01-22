Basis
=====

#. Wechseln in das Vezeichnis plone/plone43_buildout/src
#. Produktstruktur eines dexterity-Moduls Anlegen mit::

    ../bin/zopeskel dexterity
    …
    Enter project name (or q to quit): zchl.shop

    Expert Mode? (What question mode would you like? (easy/expert/all)?) ['easy']: all
    Project Title (Title of the project) ['Example Name']: ZChL-Shop
    Version (Version number for project) ['1.0']: 
    Description (One-line description of the project) ['']: Shop for the ZChL
    Register Profile (Should this package register a GS Profile) [True]: 
    Long Description (Multi-line description (in ReST)) ['']: Shop for the ZChL
    Author (Name of author for project) ['']: Thomas Heisel, Alwin Shronen
    Author Email (Email of author for project) ['']: heiselth@mx.uni-saarland.de
    Zip-Safe? (Can this project be used as a zipped egg? (true/false)) [False]: 
    Zope2 Product? (Are you creating a product for Zope2) [True]: 

#. Neuer Eintrag in devel.cfg::

    develop =
       src/zchl.shop

    [instance-base]
     eggs +=
       zchl.shop

#. buildout ausführen::
    
    bin/buildout -vc devel.cfg

#. Starten der Instanz im Vordergrund

   ::

    $ ./bin/instance fg

   Dies führt zu folgender Fehlermeldung::

    ZopeXMLConfigurationError: File "/home/plone/plone43_buildout/src/zchl.shop/src/zchl/shop/configure.zcml", line 14.2
    ConfigurationError: ('Unknown directive', u'http://namespaces.zope.org/grok', u'grok')

#. ZopeXMLConfigurationError beheben

   Hierfür löschen wir in der Datei ``src/zchl.shop/src/zchl/shop/configure.zcml`` die folgende Zeile::

    <grok:grok package="." />

