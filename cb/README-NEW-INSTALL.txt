+-------------------------------------------------------------------------+
|                                                                         |
| New Installation Readme file for the Community Builder Suite, CB 1.9    |
| This file contains instructions that should be followed for new         |
| (first-time) CB installations.                                          |
|                                                                         |
| Copyright 2004-2012 Beat, MamboJoe/JoomlaJoe and CB team on             |
| joomlapolis.com.                                                        |
| This component is released under the GNU/GPL version 2 License and      |
| parts under Community Builder Free License.                             |
| All copyright statements must be kept and derivate work must            |
| prominently acknowledge original work on web interface and on website   |
| where downloaded.                                                       |
|                                                                         |
|                     Joomla/Mambo Community Builder 1.9                  |
|             native for Joomla! 3.0.x, 2.5.x, 1.5.x and 1.0.x            |
|                            Mambo 4.5.0 - 4.6.5.                         |
|                                                                         |
|                           Now supports Joomla 3.0                       |
|                                                                         |
+-------------------------------------------------------------------------+

WARNING - The com_comprofiler.zip package is over 2M in size.
          If when trying to install you get a Joomla message:
          "There was an error uploading this file to the server.",
          then check that your PHP upload_max_filesize is at least
          4M (recommended 16M) in your php.ini file.
          Use Joomla backend to check your PHP Information settings:

          - Joomla 3.0.x -> System -> System Information -> PHP Information
          - Joomla 2.5.x -> Site -> System Information -> PHP Information
          - Joomla 1.5.x -> Help -> System Info -> PHP Information 
          - Joomla 1.0.x -> System -> System Info -> PHP Info

          and search the page for 'upload_max_filesize' to verify that 
          value is more than 2M. If not, then search same page for 
          'Loaded Configuration File' to see the actual php.ini file
          that needs to be updated. If in doubt ask your hosting
          helpdesk for assistance. 

IMPORTANT - CB 1.9 must be installed on a PHP 5.0 or better environment
(PHP 5.2+ recommended). CB 1.9 will **not** install on PHP 4.0.
MYSQL 5.0 or better required. CB DOES NOT WORK ON MICROSOFT SQL SERVER.

KNOWN ISSUES: CB related 'Menu Item Type' displayed in Joomla 3.0/2.5
              menu Item creation always shows 'Logout action'. 
              This is a Joomla bug that has been reported to Joomla team 
              and can be safely ignored as the link created internally 
              is the correct one.
              ---
              During the CB 1.9 component installation process 
              on a Joomla 2.5
              you might briefly see a 
              "Failed deleting pluginfiles.tgz" error during the first 
              phase of installation. This is to be ignored.
              ---
              When adding new users in backend of Joomla 3.0/2.5 using the
              CB User Manager, 2 welcoming email messages
              will be sent to user (one from CB and one from Joomla). 
              This appears to be an issue with
              Joomla API. You can turn this off by setting the value of the
              User - Joomla! plugin Notification Mail to User parameter to No              

IMPORTANT - This component does not work with any other registration or 
login modules or hacks. It is recommended that you uninstall all such 
modifications as the effects of using them with this component are 
unknown.

IMPORTANT - As for any installation: FIRST BACKUP your database and files.

SUMMARY OVERVIEW
----------------
1)  Install com_comprofiler component (also known as the CB component).
2)  Install mod_cblogin module (also known as the CB Login module).
3)  Install mod_comprofilerModerator module (also known as the Workflow module).
4)  Install mod_comprofilerOnline module (also known as the CB Online module)
5)  Enable CB Login, CB Workflows and CB Online  modules 
    (see detailed instruction for Joomla 3.0/2.5 related module positioning 
    on default Joomla 3.0/2.5 template)
6)  Select Name Style parameter from Community Builder Configuration and Save.
    Run Community Builder Synchronize Users tool.
7)  Disable Joomla/Mambo login modules
8)  Add new Public menu item to Community Builder component *** IMPORTANT ***
9)  Add new User List menu item
10) Run Load Sample Data tool (optional)
11) Adjust Community Builder and Joomla/Mambo CMS settings to allow 
    registrations only through Community Builder
12) Done!

You can also read the CB1.9_Installation.pdf document included in the
distribution package or consider supporting CB team as an Advanced or
Professional member to get the full documentation and many more benefits: 
http://www.joomlapolis.com/cb-solutions/add-ons
http://www.joomlapolis.com/cb-solutions/incubator

DETAILED INSTRUCTIONS TO INSTALL CB 1.9
---------------------------------------

1)  Install com_comprofiler.zip as a component. (see notes below first)
    NOTE: Please be patient. com_comprofiler.zip is large (2.0+ MB) and takes
    time to upload and install (sometimes over 5 minutes on large sites !).
    The installation of CB will be done automatically 
    in 2 pages (2 step process), which will load automatically.
    Please wait for the green message saying that installation is finished.
    In case of problems, see troubleshooting section further down in this 
    file.

    NOTE: PHP Safe mode must be off for component and plugins installation
    in Joomla! 1.0.x and Mambo.

    NOTE: Mambo 4.6.0 - 4.6.5 don't handle multiple xml files properly, so:
    a) you need to first unzip com_comprofiler.zip, remove the files ending
    with j.xml and g.xml and the access.xml file and re-zip before installing 
    on these Mambo versions.
    b) For each module used below, you need to unzip the package, replace
    the XML file which is inside the "files" folder by the one which is
    outside that folder, and then rezip the "files" folder for Mambo 4.6.

    IMPORTANT: if install fails, see "In case of failed install section" 
    below.

2)  Install mod_cblogin.zip as a module.

    IMPORTANT if you use the core Joomla or Mambo login module the 
    users will become out of sync with community builder.

    NOTE: Go to Joomla/Mambo Admin->Components->Community Builder->Tools
    And use the synchronize users tool to synchronize your user 
    database if this happens.

3) Install mod_comprofilerModerator.zip as a module
   This module is also known as the CB Workflows module and it is used to
   manage front-end moderation actions.
   (Optional Module, only needed if using moderator features).

4) Install mod_comprofilerOnline.zip as a module
   This module is also known as the CB Online module and it is used to
   produce and display a list of currently logged in users with links
   back to their CB user profile page.
   (Optional Module, displays list of online users).

5) Enable the cblogin login module (CB Login), and other CB modules
   from the administration backend (go to modules->site modules then
   click on publish red cross or click on module name to set params).
   
   NOTE: On Joomla 3.0/2.5 the 'left' module position will not show-up in
   ----  the default template. You need to set the module to position-7.

6) Go to Joomla/Mambo Admin->Components->Community Builder->Configuration
   and at least choose the user name type (first/lastname mode choice)
   corresponding to how you want to split or not split the existing users'
   name during existing users synchronization of the next installation step.
   Make sure to click "Save" on the configuration page.

6b)Go to Joomla/Mambo Admin->Components->Community Builder->Tools
   And use the "Synchronize users" tool to synchronize CB with Joomla.
   or Mambo.

7) Disable the Standard Joomla/Mambo Login Module. To do that, go to the
   administration backend then:
   - in Mambo/joomla 1.0 go to modules->site modules then click on the 
     green publish checkmark of "Login form" (mod_login) so that it 
     becomes a red cross.
   - in Joomla 1.5 go to Extensions->modules then click on the green 
     "Enabled" checkmark of "Login form" (mod_login) so that it becomes 
     a red cross.
   - in Joomla 3.0/2.5 go to Extensions->Module Manager and unpublish all
     instances of Login module (use Type drop-down filter to find them).

8) Add a new user menu item to the "User Menu" for Community Builder:
   (this will be the link to the user's profile page).
   For this, go to "Menus" -> "User Menu", click New, then:
   - in Mambo/joomla 1.0 select "component", "Community Builder 
     (comprofiler)", leaving access public for the item, 
     give a name and save.
   - in Joomla 1.5 click in internal links "Community Builder", 
     then "User Profile",
     leave access public for the item, give a title and alias and save.
   - in Joomla 3.0/2.5 go to User Menu (if sample data was installed)
     or any other Menu published for Registered group and 
     click "(+) Add New Menu Item" for J 2.5 or click " + New" for J 3.0, 
     then click the
     Select button next to the "Menu Item Type *" field to reveal the
     "Select a Menu Item Type:" pop-up window. Select the
     "User Profile (mandatory)" item in the comprofiler section.
     Give it a Menu Title (example: "My CB Profile") and set the
     "Access" drop-down field to "Public". Then click "Save & Close".
     
     KNOWN ISSUE: When you create any CB related menu item in Joomla 3.0/2.5
     -----------  the Menu item type field always shows 'Logout action'
                  This is a Joomla 3.0/2.5 bug which has been reported.
                  You can safely ignore this as the populated link is
                  the correct one.
      
   NOTE: This is not a security issue, CB checks access. 
         As you don't want this menu item to appear publicly, 
         you can put it in the User Menu as explained in this step, 
         or another menu with Registered access level at least.

9) Add a list menu item:
   (this will be the link to the searchable users-listing).
   For this, go to "Menus" -> "User Menu" (for non-public lists) or
   "Menus" -> "Main Menu" (for public lists), click New, then:

   - in Joomla 3.0/2.5 select "Users lists" item in the comprofiler section
     when selecting a "Menu Item Type *" for your menu. 

   - in Joomla 1.5 click internal links "Community Builder", 
     then "Users-list", leave parameters as is, and save

   - in Mambo/Joomla 1.0 select Link-URL / External-URL and point it to 
     index.php?option=com_comprofiler&task=usersList 
     (no 'http://domain' name) and save.

    NOTE: if you want the list to be accessible publicly, make this
          menu entry public (and make also public the one under point 8)

    NOTE: if you make the menu being the first of the main menu it will
          become the site's homepage.

10) [OPTIONAL]
    Go to Joomla/Mambo Admin->Components->Community Builder->Tools
    And use the "Load Sample Data" tool to pre-populate fields with
    standard user contact fields (address, phone, etc), and also create a
    default users list.

    NOTE: To edit this default users list/add other users lists: Go to
          Joomla/Mambo Admin->Components->Community Builder->List management
          and change/add list(s) with the corresponding access level.
          Make sure they are published.

11) [RECOMMENDED]
    If you want to allow registrations only through Community Builder:
    - in Admin->Components->Community Builder->Configuration->Registration:
      set "Allow User Registration" to 
      "yes, independently of global site setting"

    - in Joomla 3.0/2.5 Administration->Users->User Manager click the
      Options button and set 'Allow User Registration' parameter to 'No'.

    - in Joomla 1.5 Admin->Site->Global Configuration->System:
      set "Allow User Registration" to "No".

    - in Joomla 1.0/Mambo Admin->Site->Global Configuration->Site 

12) Done !

Pleas consider supporting the CB team by becoming an Advanced, Professional
or Developer member or purchasing CBSubs - the most powerful membership
subscription management solution for Joomla!.

=====================================================================
TROUBLESHOOTING section

IN CASE OF FAILED COMPONENT INSTALL:
- Blank screen: check error logs of your web-server, or enable PHP errors 
  display.
  Or try both fixes below blindly.

- Maximum Execution time reached:
   On very slow servers, IF installation timeouts (not seen yet): you
   can fix that as follows: Open file:

   - joomla 1.5//2.5/3.0: administrator/index.php

   - joomla 1.0/mambo: administrator/index2.php

   and add line
   set_time_limit( 240 );
   right after the <? line, remove directories components/com_comprofiler
   and administrator/components/com_comprofiler and re-install.

- Memory exhausted error (sometimes Error 500):
   If you get a Memory exhausted error, simply add line (similarly as above):
   ini_set( 'memory_limit', '16M' ); @ini_set( 'memory_limit', '32M' );
   to index2.php or index.php file (depending on Joomla version).

- Check that your PHP 'upload_max_filesize' parameter (in your php,ini) is
  set to something greater than 2M. If not try increasing and reinstalling.
  
- If component installation step 2 failed: Do not panic ! :

  Just access CB component from backend, it's safe.

  In all backend tasks there is a test if step 1 has been completed or not.

  - If you don't see any warnings at top of screen then installation 
    completed successfully.

  - if you see a warning like:

    "Warning: file 'components/com_comprofiler/pluginsfiles.tgz' still 
    exists.
    This is probably due to the fact that first installation step did not
    complete, or second installation step did not take place. If you are 
    sure that first step has been performed, you need to execute second 
    installation step before using CB. You can do this now by clicking here:
    (link: please click here to continue next and last installation step)."

    Then you can just click on the link to complete the second step. 
    This step simply uncompresses that 'pluginsfiles.tgz' file into the 
    same place and then deletes the file. The second step can be safely 
    redone.

  In case it still doesn't work, it's probably a permissions problem 
  either on the folder 'components/com_comprofiler', not allowing the 
  webserver to write into (or in case of joomla 2.5/1.7/1.5 ftp 
  installer active, the credentials not being correct).

  You can fix that by fixing the permissions of that folder, 
  and retry step 2.

  At last resort you can uncompress pluginsfiles.tgz, and rename the
  resulting directory 'pluginsfiles' to 'plugin' at the same place.
  You need to make sure that the plugin and all directories inside
  plugin (user, templates, language) are also writable, otherwise you
  won't be able to install CB plugins at a later stage.


UNINSTALLING CB

To uninstall CB, simply uninstall CB Component and CB modules from your CMS.
User data will be preserved in MySQL tables starting with prefix_comprofiler.
Main CB Configuration is deleted on uninstall of CB component as it is
stored in file administrator/components/com_comprofiler/ue_config.php .
CB module configurations are deleted on module uninstall, per CMS methods.
CB plugins, tabs and field configurations, as well as user data is preserved
for reinstallation (see README-UPGRADE.txt for details upgrading/reinstalling).
To remove all database records, delete tables starting with prefix_comprofiler
in a MySQL tool like PhpMyAdmin.

-----------------------------------------------------------------------

KNOWN PROBLEMS:

- with Joomla 3.0/2.5 during the first phase of the comprofiler component
  installation you may briefly see a red error on the Joomla backend stating
  "Failed deleting pluginsfiles.tgz" - you can safely ignore this.

- check www.joomlapolis.com forums for latest known issues.

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
and see relevant forum posts.

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
