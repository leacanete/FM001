+-------------------------------------------------------------------------+
|                                                                         |
| New UPGRADE Readme file for the Community Builder Suite, CB 1.9         |
| This file contains instructions that should be followed when upgrading  |
| from a previous CB installation.                                        |
|                                                                         |
| Copyright 2004-2012 Beat, MamboJoe/JoomlaJoe and CB team on             |
| joomlapolis.com.                                                        |
| This component is released under the GNU/GPL version 2 License and      |
| parts under Community Builder Free License.                             |
| All copyright statements must be kept and derivate work must            |
| prominently acknowledge original work on web interface and on website   |
| where downloaded.                                                       |
|                                                                         |
|                      Joomla/Mambo Community Builder 1.9                 |
|              native for Joomla! 3.0.x, 2.5.x, 1.5.x and 1.0.x           |
|                             Mambo 4.5.0 - 4.6.5.                        |
|                                                                         |
|                           Now supports Joomla 3.0.x                     |
|                                                                         |
+-------------------------------------------------------------------------+	

WARNING - The com_comprofiler.zip package is over 2M in size.
          If when trying to install you get a Joomla message:
          "There was an error uploading this file to the server.",
          then check that your PHP upload_max_filesize is at least
          4M (recommended 16M) in your php.ini file.. 

IMPORTANT - CB 1.9 must be installed on a PHP 5.0 or better environment
(PHP 5.2+ recommended). CB 1.9 will **not** install on PHP 4.0.
MYSQL 5.0 or better required. CB DOES NOT WORK ON MICROSOFT SQL SERVER.

IMPORTANT - Please check the Joomlapolis forums for latest identified
issues when used on various Joomla environments.

IMPORTANT - This component does not work with any other registration or 
login modules or hacks. It is recommended that you uninstall all such 
modifications as the effects of using them with this component are 
unknown.

IMPORTANT As for any upgrade: FIRST BACKUP your database and files.

Joomla related note:
===================
f you are on Joomla 1.5, 1.6 or 1.7 and plan to migrate/upgrade to the
latest Joomla 3.0.x or 2.5.x, you should:- first upgrade your Community Builder version to CB 1.9,- make sure that you have latest CB Team plugins and other 3/0/2.5-compatible Joomla extensions- and then migrate/upgrade your Joomla version. (if migrating from Joomla 1.5, using jUpgrade will also migrate CB and CB plugins)

============================================================
UPGRADING FROM CB 1.2 or better ON A JOOMLA 1.5 ENVIRONMENT
UPGRADING FROM CB 1.8.1 ON A JOOMLA 2.5 ENVIRONMENT
============================================================

1)  Install new CB component (com_comprofiler.zip) from 
    your CB 1.9 distribution package.
    Do not uninstall existing CB component.
    Previous installation and database will be updated automatically
    and all CB fields, Tabs, Plugins, Lists, Configuration and user profile
    data will be preserved.
2)  Install new CB Login module (mod_cblogin.zip package)
    from your CB 1.9 distribution package.
    Do not uninstall existing CB Login module..
3)  Install new CB Workflow module (mod_comprofilerModerator.zip package)
    from your CB 1.9 distribution package.
    Do not uninstall existing CB Workflow module.
4)  Install new CB Online module (mod_comprofilerOnline.zip package) 
    from your CB 1.9 distribution package.
    Do not uninstall existing CB Online module.
5)  Run CB Tool checks on CB database.
6)  Done!

Note: This method preserves all installed user plugins and parameters.
      Only core code files are updated.


IMPORTANT - If you are not on a Joomla 2.5/1.7/1.5 environment or you are
upgrading from a CB version prior to CB 1.3.1, you should
have all Community Builder plugin installers that you 
installed before at hand, or use the expert installation procedure below.
DO NOT uninstall plugins that you want to keep after upgrade.

UPGRADES: DIRECTORY/FILE OWNERSHIP/PERMISSIONS (common Joomla/Mambo problem):
If you have uploaded Community Builder by ftp to the web server without
changing directory permissions or ownership, you should either:
- ask your hoster to do so first, so that the webserver process running
  Joomla/Mambo is able to delete old files on uninstall in step 3 below
  and create and write new directories and files.
- or for Mambo and Joomla 1.0 only consider the expert upgrade 
  (instructions below)

Alternatively for upgrading only, if you have ftp, take a look at
alternative 5-steps EXPERT upgrade instructions at end, otherwise read on.

IMPORTANT - This component does not work with any other registration or 
login modules or hacks. It is recommended that you uninstall all such 
modifications as the effects of using them with this component are 
unknown.

===================================================================
UPGRADING FROM EARLIER THAN CB 1.2 RC VERSIONS 
===================================================================

To upgrade to CB 1.9 from CB 1.1 or CB 1.2 RC on a Joomla 1.0.x
or Joomla 1.5.x environment you need to follow on of the following:

 - EXPERT FTP UPGRADE PROCESS or the
 - MANUAL UNINSTALL/INSTALL PROCESS

EXPERT FTP UPGRADE PROCESS:
---------------------------
NOTE:
----> You will need to download the extra CB 1.9 relevant 
      cb_expert_files_only_*.tar.gz
      file separately from the Free download area on Joomlapolis

SUMMARY OVERVIEW OF EXPERT FTP UPGRADE PROCESS
----------------------------------------------
a) backup all
b) untargzip cb_expert_files_only_YOUR_MAMBO-JOOMLAVERSION.tar.gz directly to
   your main website folder
   or 
   untarzip (using 7zip like program) to your local PC/Mac to 
   reveal 3 folders: administrator, components, modules
   upload 3 folders using any ftp client to your main website root
   over-writing same folders (don't worry - only CB files will be changed)  
c) remove tar.gz file (if you untarzip directly), 
   and if joomla 1.5: 
   remove modules/mod_cblogin/*j.xml modules/mod_comprofiler*/*j.xml
d) disable joomla registration and activate CB registration if needed
e) use CB tools to check all databases and fix (CB, fields, plugins)
f) open CB config, check name-display type, and save CB configuration
g) check tabs and fields positions 
   (if your first installed CB version was before 1.0.0 stable)
h) if upgrading from very old CB 1.0 beta 3 restore avatars

DETAILS OF EXPERT FTP UPGRADE PROCESS
-------------------------------------
a) backup files and SQL database, including ue_config.php
   (if upgrading of BEFORE very old CB 1.0 beta 3 check step 3b below).
b) untargzip the package:
   - Mambo/Joomla 1.0: cb_expert_files_only_m_4_j_1.0.tar.gz
   - Joomla 1.5: cb_expert_files_only_j_1.5.tar.gz
   and overwrite corresponding CB 1.1 STABLE files in:
   - administrator/components/com_comprofiler  
     (excluding ue_config.php which should stay from your previous release)
   - components/com_comprofiler
   - modules 
   This can be done by putting this cb_expert_files_only... file
   in joomla or mambo main folder and typing:
   tar -xvzf cb_expert_files_only_m_4_j_1.0.tar.gz
   or depending on version:
   tar -xvzf cb_expert_files_only_j_1.5.tar.gz
   
   You can also unzip - untar locally using 7zip program and
   upload 3 folders (administrator, components, modules) to
   your website root using any ftp client.
   
c) remove this tar.gz file: rm cb_expert_files_only_*.tar.gz
   (in case you used the tar method)

   If you installed any CB 1.2 RC release in Joomla 1.5 ONLY:
   delete following 3 files:
   modules/mod_cblogin/mod_cbloij.xml
   modules/mod_comprofilermoderator/mod_comprofilermoderatoj.xml
   modules/mod_comprofileronline/mod_comprofileronlij.xml
   
d) follow step 11 of README-NEW-INSTALL.txt file if needed.
   --> Adjust Community Builder and Joomla/Mambo CMS settings to allow registrations
       only through Community Builder

e) go to Components -> Community Builder -> Tools and 
   click "Click here to Check Community Builder Database"
   you should see some output in red, like 
   (this example is for upgrade from CB 1.1, but it also works for any previous version):
	 Database structure differences:
	 ...
	 Table #__comprofiler_fields Column tablecolumns does not exist
	 Table #__comprofiler_fields Rows fieldid = 41 : Field tablecolumns = "" 
	 instead of 'name'
	 Table #__comprofiler_fields Rows fieldid = 26 : Field name = NA instead
	 of 'onlinestatus', Field tablecolumns = NA instead of ''
	 ...
	 Table #__comprofiler_lists Column params does not exist
	 Table #__comprofiler_sessions does not exist
	 ...
   Click on the link at bottom "Click here to Fix all database differences 
   listed above", and you should see in green:
   "Database fix has been performed successfully"
   Check again database to make sure all is now green.

   Repeat same for CB fields and for CB plugins database checks and fixes.

f) do steps 6 of the README-NEW-INSTALL.txt file (at least the save part).
   --> Select Name Style parameter from Community Builder Configuration and Save.
       Run Community Builder Synchronize Users tool.


g) if your first installed version of CB was BEFORE CB 1.0.0 STABLE:
   check and adjust if needed fields and tabs-positions.
   The upgrader will do best efforts remappings, but
   if you have edited tables manually, you might have to re-arrange manually
   fields and tabs.

h) if upgrading of BEFORE very old CB 1.0 beta 3 check step 7b below.


MANUAL UNINSTALL/INSTALL UPGRADE PROCESS:
-----------------------------------------
NOTE:
----> FOLLOWING APPLIES FOR UPGRADES FROM CB 1.1 and CB 1.2 RC releases:
      SEE FIRST EXTRA INFO FOR UPGRADES FROM CB 1.0 AT BOTTOM OF THIS DOCUMENT:

SUMMARY OVERVIEW OF UNINSTALL/INSTALL UPGRADE PROCESS
-----------------------------------------------------
1)  Save your ue_config.php file (to be able to restore later): it is
    located in administrator/components/com_comprofiler/ue_config.php
2)  Make sure you have all extra CB plugin packages used on your
    site (you will need these these later in the process).
    Uninstall CB component.
3)  Install new CB component from your CB 1.9 distribution package.
    Restore your saved ue_config.php file.
4)  Take notes regarding your existing parameter settings for the
    existing CB Login module (you will need to reconfigure these
    parameters manually later on).
    Uninstall your existing CB Login module and install the new one
    contained in the CB 1.9 distribution package.
    After installations, publish and configure parameters (check
    notes you kept earlier).
5)  Follow previous step 4 for existing CB Workflow - Moderation module.
6)  Follow previous step 4 for existing CB Online module.
7)  Remove existing CB related menu items and create new ones.
    Verify that the removed menu items are also removed from trash.
8)  Reinstall any additional plugins you had (see step 2).
9)  Inspect existing user lists and make needed changes.
10) Run CB Tool checks on CB databases.
11) Done!


DETAILS OF UNINSTALL / INSTALL UPGRADE PROCESS
----------------------------------------------

1)  If upgrading from any previous version you may want to make a copy of 
    your configuration file:
    administrator/components/com_comprofiler/ue_config.php
    and of your language file and/or cb template if you modified them,
    off-server, or at very least outside the com_comprofiler directories.
   
    IMPORTANT As for any installation: BACKUP FIRST your database and files.

2)  Check in joomla/mambo installer that the directories and directory
    contents are writable first:
    - components ( and components/com_comprofiler )
    - administrator/components (and administrator/components/com_comprofiler)
    - modules ( and modules/mod_cblogin )

    IMPORTANT Make sure you have all extra CB plugin packages used on your site
    (you will need these these later in the process)

    Then uninstall Community Builder (comprofiler).
   
    NOTE: Don't uninstall CB plugins (this will keep their parameters).
    This WILL NOT DELETE:
    - any data in the database
    - any parameters for fields, tabs, plugins, user data;
    But IT WILL DELETE additional CB plugin program files only (not their
    parameters). That's why you will need the CB plugin installers.
    IMPORTANT: You will need to REINSTALL these CB plugins later at last
    step.
    WARNING: Some third-party CB plugins come with modules and/or mambots
    which do not test for the CB plugin being installed, which can
    result in errors or blank screens. If you don't reinstall the
    corresponding CB plugin you may need to unpublish or uninstall
    the corresponding modules and/or mambots.

3)  Follow step 1 from the README-NEW-INSTALL.txt file 
    (Install com_comprofiler.zip as a component)

3b) You can now replace the default ue_config.php
    file by the ue_config.php that you saved in step 1) above.
    IMPORTANT: once you have restored your ue_config.php file, you need
    to go to CB configuration and SAVE the configuration, so that core
    names fields publishing is updated correctly.


    NOTE: In CB 1.9, in users-lists, the "public frontend" and the
    "public backend" "User Groups to Include in List" are not expanded
    anymore to all the corresponding frontend, respectively backend
    user levels, so you need to select them individually.

4)  You need to uninstall mod_comprofilerlogin or 
	  mod_cblogin452 or mod_cbloginRC2 or mod_cblogin 
    (depending on the CB version you have installed) and 
	  install the new mod_cblogin, as it contains added security needed by CB.
	  Before you uninstall the login module, you should take a note of the 
	  module parameter settings you have configured, since you will need to
	  redo these after reinstalling. 
	  After reinstallation make sure you enable/publish the module and 
	  reconfigure and parameter settings you need. 

    (see step 2 of the README-NEW-INSTALL.txt file for more detailed 
    instructions of login module install process)
   
5)  You need to uninstall and reinstall mod_comprofilerModerator.
	  Before you uninstall the mod_comprofilerModerator module, you should take 
    a note of the module parameter settings you have configured, 
	  since you will need to redo these after reinstalling. 
	  After reinstallation make sure you enable/publish the module and 
	  reconfigure and parameter settings you need. 

    (see step 3 of the README-NEW-INSTALL.txt file for more detailed 
    instructions of mod_comprofilerModerator module install process)

6)  You need to uninstall and reinstall mod_comprofilerOnline.
	  Before you uninstall the mod_comprofilerOnline module, you should take a 
 	  note of the module parameter settings you have configured, 
	  since you will need to redo these after reinstalling. 
	  After reinstallation make sure you enable/publish the module and 
	  reconfigure and parameter settings you need. 

    (see step 4 of the README-NEW-INSTALL.txt file for more detailed 
    instructions of mod_comprofilerOnline module install process)
 
7)  Remove your existing CB menu items, and create new ones following 
    steps 8 and 9 of the README-NEW-INSTALL.txt file

8)  If you had additional CB plugins installed (see step 2 above), 
    you will need to reinstall them.
    Install additional plugins that you had before upgrading or check
    out additional plugins available at http://www.joomlapolis.com
    NOTE: plugins which have their parameters memorized by CB, but
          have missing program files are displayed in plugin list
          without clickable title-name, and with a barred plugin name.
          These will be displayed normally and usable again once
          plugin is installed again. If you don't wish to do so, you
          can delete the plugin parameters by selecting delete.

9)  If you have existing CB user lists, check that the fields that you want 
    to see in users-list are also on profile. 
    That was also the case earlier, except
    for username, name and formatted name, now it's also the case for
    those ones as well. You can do this in CB Fields manager.

10) This is a good time to check the CB database in
    Components->Community Builder->Tools->Check Community Builder Database
    Also after reinstalling any extra plugins you had (see step 8)
    check db of plugins and of fields (extra options in Tools menu).

11) Done !


EXTRA INFO FOR UPGRADES FROM BEFORE CB 1.1: UNINSTALL/INSTALL PROCESS:
----------------------------------------------------------------------

0) If upgrading from a version BEFORE very old CB 1.0 beta 3, backup the
   components/com_comprofiler/avatars directory.
   They will be deleted when you uninstall Community Builder.
   This first step is NOT needed for upgrade from CB beta 4, RC1, RC2,
   1.0 or later

3b)IMPORTANT: Check your registration page: the ordering of tabs is
   now better respected for registrations too, so tabs may have moved
   to previous versions. Typically, username is not anymore mandatorily
   the first field on the registration page. The new ordering is now:
   a) registration ordering of tab (new: can be set in "edit tab")
   b) position of tab on user profile (top-down, left-right)
   c) ordering of tab on position of user profile
   d) ordering of field within tab position of user profile.

7b)If upgrading from a version prior to 1.0 beta 3 place all the 
   images that were once in components/com_comprofiler/avatars into 
   images/comprofiler/ directory 
   (this is related with actions taken in step 0 above)

11b) if upgrading from BEFORE CB 1.0.0 STABLE, check and adjust 
     if needed fields and tabs-positions. 
     The upgrader will do best efforts remappings, but
     if you have edited tables manually, you might have 
     to re-arrange manually fields and tabs.

-----------------------------------------------------------------------
KNOWN PROBLEMS:

During module installations over existing install in Joomla 1.5.15 environment
you might see the following notices:

Notice: Undefined variable: 
row in ...\libraries\joomla\installer\adapters\module.php on line 252

Notice: Trying to get property of non-object in
...\libraries\joomla\installer\adapters\module.php on line 252

This is a Joomla bug identified at:
joomlacode.org/gf/project/joomla/tracker...racker_item_id=17878

During component upgrading on Joomla 1.7/2.5 you might briefly
see the following warning message during the first install step of CB:

Failed deleting pluginsfiles.tgz

This error can be ignored as CB will remove this file during next step of its
installation process


NOTE: Community Builder includes a version checker that accesses
joomlapolis website to query for the latest version of CB and, if
available, latest information displayed together with the latest
version number in backend. This query doesn't disclose any private
information. Only information needed for this standard http query
are version number and referrer (site address). If you don't have
Internet access, after a timeout of 20 to 90 seconds an error message
will be displayed instead of latest version when showing your config
or "about CB" from the backend. You can switch this check to "manual"
in CB configuration: "integration" tab (Not recommended).

FOR DOCUMENTATION, SUPPORT AND LATEST NEWS VISIT: 
http://www.joomlapolis.com 

FOR BUG REPORTS AND FEATURE REQUESTS VISIT: 
http://www.joomlapolis.com/
and see relevant CB 1.9 forum posts.

LICENCE:
Community Builder is licensed under GNU/GPL version 2 as a whole,
provided that some parts used are subject to other licenses for which
CB Team has rights of use for Community Builder.

TRADEMARK:
Community Builder is a trademark of the authors of Community Builder
at www.joomlapolis.com .
You are welcome to use the "Community Builder" trademark to refer to
this software or manuals provided that you make clear that you are
not the Community Builder project, that you do not represent it,
and do not incorporate the trademark or logo into your own trademarks.
If you have any questions regarding the use of our trademarks, please
contact us using the contact form of www.joomlapolis.com .