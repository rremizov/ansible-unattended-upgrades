.. sectnum::

Unattended Upgrades
===================

Configure unattended upgrades.

Requirements
------------

- Debian 10, 11, 12

Role Variables
--------------

``unattended_upgrades_enable_for``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

List of the distributions which will have unattended upgrades enabled.

``unattended_upgrades_disable_for``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

List of the distributions which will have unattended upgrades disabled.

``unattended_upgrades_origins_pattern``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

List of patterns for the ``Unattended-Upgrade::Origins-Pattern``.

``unattended_upgrades_package_blacklist``
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

List of patterns for the ``Unattended-Upgrade::Package-Blacklist``.

Example
-------

.. code:: yaml

    unattended_upgrades_enable_for:
      - distribution: Debian
        version: "10"
      - distribution: Debian
        version: "11"
      - distribution: Debian
        version: "12"

    unattended_upgrades_disable_for:
      - distribution: Ubuntu
        version: "18"

    unattended_upgrades_origins_pattern:
      - {origin: "${distro_id}", codename: "${distro_codename}", label: "${distro_id}-Security"}
      - {origin: "${distro_id}", codename: "${distro_codename}", label: "${distro_id}"}
      - {origin: "${distro_id}", codename: "${distro_codename}-updates"}

    unattended_upgrades_package_blacklist:
      - linux-image
      - libc6
      - libc6-dev
      - libc6-i686
      - postgresql
      - mariadb-server
      - mysql-server
      - redis-server
