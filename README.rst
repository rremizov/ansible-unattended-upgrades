.. sectnum::

Unattended Upgrades
===================

Configure unattended upgrades.

Requirements
------------

- Debian 8, 9, 10

Role Variables
--------------

``unattended_upgrades_enable_for``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

List of the distributions which will have unattended upgrades enabled.

``unattended_upgrades_disable_for``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

List of the distributions which will have unattended upgrades disabled.

Example
-------

.. code:: yaml

    unattended_upgrades_enable_for:
      - distribution: Debian
        version: "8"
      - distribution: Debian
        version: "9"
      - distribution: Debian
        version: "10"

    unattended_upgrades_disable_for:
      - distribution: Ubuntu
        version: "18"
