---
layout: page
title: FusionInventory for GLPI installation
---

# FusionInventory for GLPI installation

## Get the archive for your GLPI

First, download archive the here: <http://forge.fusioninventory.org/projects/fusioninventory-for-glpi/files>

FusionInventory for GLPI tarball name follow this convention:

* fusioninventory-for-glpi-metapackage_
* GLPI major release (0.80, 0.83, 0.84, etc)
* a '+' symbol
* FusionInventory release

## Update

You *must* *FIRST* disabled the FusionInventory plugins and move somewhere else the FusionInventory plugins. This to ensure deprecated files will properly be removed.

[[!template  id=warning text="Don't click on *UNINSTALL* link. If you do this, you will LOOSE all FusionInventory data."]]

## Installation

[[!template  id=warning text="If a previous FusionInventory version is already installed, you must read the Update section."]]

It's also always a good idea to do a backup of your database.

* Uncompress the archive into the plugin folder of GLPI. File list seems to be like :

    - D glpi
      - D plugins
         - D fusioninventory
            - F index.php
            - F hook.php
            - D front
            - D inc
            - …

* Connect to _GLPI_
* Go in the menu _Setup_ > _Plugins_
* Install the plugins
* Activate FusionInventory 

These operations will create or upgrade the database and set the correct rights on the plugin.
Do the same for all fus* plugins

## Initial configuration

Once the plugin is activated, you will have to go on the _Plugins > FusionInventory > General configuration_
page to set the *Service URL*. You need to enter the location of your GLPI server, for example `http://glpi.mydomain/`.

![](images/service_url.png)

Once these is done, you can [[install your first agent|documentation/agent/installation]].

### Options Detail

SSL-only for agent: send an error response to an agent when this agent communicates to the server without SSL.

## Security

[[!template id=warning text="We strongly recommend to activate SSL on the
server side to protect human user communications, and eventually agent
communications too. See [[here|documentation/security]] for details."]]

