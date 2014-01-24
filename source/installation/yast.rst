====
YAST 
====

Repositories hinzufuegen
------------------------

.. todo:: YAST-Repositories hinzufuegen

Für einige der Repositories ist es erforderlich, den LDAP-Account einzugeben.
Dabei ist der Account-Name ohne Domain-Angabe anzugeben.

Pakete installieren
-------------------

Sofern neue YAST-Pakete installiert werden, die in Python zur Verfügung stehen
sollen, ist nach der Paket-Installation auch Python neu zu installieren.

Die folgenden Systempakete benötigt Plone. Diese sind mit YAST zu
installieren:

* ``gcc``
* ``gcc c++``
* ``make``
* ``zlib-devel``
* ``openssl-devel``
* ``libxml2-devel``
* ``libxslt-devel``

Folgende YAST-Pakete erleichtern die Entwickklung:

* ``git``
* ``readline``

Für LDAP werden folgende Pakete benötigt:

* ``openldap2-devel``
* ``libldap-2_X-Y``
* ``libopenssl-devel``

