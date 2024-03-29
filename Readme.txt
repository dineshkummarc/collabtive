
### Requirements ###
Server:
- PHP 5.2 or higher (Recent stable build recommended)
- MySQL 4 or higher

It is recommended to run Collabtive on LAMP (Linux, Apache, MySQL, PHP) servers.
Windows Servers may work, but are not supported as well.

Client:
- Firefox 3.6, Internet Explorer 7/8/9, Opera 9/10, Safari, Chrome
- Javascript enabled

### Installation instructions ###
    1. Unpack the archive.
    2. Upload everything, including the empty /files and /templates_c folders, to your server.
	   (Optionally you need to create /templates_c and /files manually before installation.)
	3. Make the following folders & files writable:
		- /templates_c
		- /files
		- /config/standard/config.php
	4. Create a new MySQL database for Collabtive.
	5. Point your browser to install.php and follow the instructions given.
	6. If the installation was successful, delete install.php and update.php.


### Update instructions ###
    1. Unpack the Collabtive Archive
    2. Retrieve your config.php from your server
    3. Put your config.php in the folder /config/standard/, replacing the blank one.
    4. Upload everything to your server, replacing any old Collabtive files
    5. Point your browser to update.php.
	6. If the update was successful, delete install.php and update.php.


### License conditions ###
Collabtive is free software under the terms and conditions of the
GNU General Public License (GPL) (Version 3).
Please see license.txt for full licensing terms and conditions.


### Credits ###
- Collabtive is (c) Philipp Kiszka
- Project coordination and support by Eva Kranz
- Artwork by Marcus Fr�hner
- Icons are partially taken from the Oxygen iconset.
- Many locales maintained by various contributors:
    - French maintained by Jean-Christophe Breboin (www.fairytree.fr)
	- Bulgarian maintained by Jordan Hlebarov
	- Chinese maintained by Hu Yanggang
	- Polish maintained by Hubert Miazek, Jakub Dyda and Maciej Smolinski
	- Serbian maintained by Vladimir Mincev
	- Turkish maintained by Mustafa Sarac

Change Log :-

Collabtive 0.7.5
+ Improved code comments
+ Streamlined user interfaces of the forms for adding and editing a milestone
+ Fixed bug in the project timetracker filter so the filtered list of timetracker entries is now sorted by date as it should be
+ Timetracker filter in user profiles now allows for selecting multiple projects instead of just a single project
+ The quickjump menu in the sidebar now has a fixed width at 100%
+ Fixed a bug where clicking cancel on the add task form would submit the form
+ Made the sliding parts of the UI a bit snappier
+ Cleaned up the desktop: only show the calendar if there are projects available
+ Extended limits for milestones
+ Fixed bug where the text of a message or task would not display correctly when adding / editing it in the single item view
+ Improved translations: Chinese, Russian
+ Refactored method getAllUsers in class.user.php
+ PHP date() compatibility for the JS calendar / datepicker
+ Fixed a small display glitch in winter
+ Disabled browserinternal forms checking to prevent conflicts with the built in forms validator
+ Added Beta version of a JSON / XML API.
+ Fixed display bug in the timetracker report
+ Optimized asynchronous queries to check for new chat messages and onlinelist updates when idle (i.e. when not browsing through collabtive). It uses a decay mechanism now to reduce the number of ajax requests to the server. This should reduce DB utilisation.
+ Compressed some large JS assets, that were previously served uncompressed, (like prototype.php) with YUIcompressor, reducing the amount of JS code to be loaded by the user
+ Fixed a broken implementation of Date.parse() in IE by using a JS version of strtotime() for the calendar
+ Fix a glitch were online users would briefly not show up in the online list
+ Fixed a bug where the "select file" in the add file dialog could not be clicked
+ Made the asyncronous deleting of items (tasks, projects) a bit faster
+ Improved the styling of the colorpicker and imagechoser in tinymce
+ Removed unwanted margin from textareas

Collabtive 0.7
+ Changed assign-to field in add task form to multi-select (was missing only when you clicked a date on the calender and chose "add task")
+ Optimized user profiles to not show the blocks for projects and time tracking when there are no entries
+ Made the use of the field Company in user profiles more user friendly
+ Added missing string "hello" to e-mail notification which a new user receives
+ Optimized the user add form to not show a label for projects, if no projects have been added, yet
+ Extended sortability of tables on desktop to My tasks: sortable by Task / Project / Days left, show mouse when hovering over column title
+ New feature: added a quickfinder to the sidebar, allowing the users to quickly switch to any of their other open projects
+ Optimized table column widths to show more of the entries in the main column
+ Optimized table alignment (content should align right, if the column only contains digits)
+ Added truncation to some views where it was missing
+ Optimized display of time track entries in user profiles
+ Optimized truncation in several views (e.g. now longer chunks of file names are shown)
+ Optimized log to show more of the entries' titles, to log actions applied to folders, to display deleted files' names, to not display log entries for actions concerning time tracking (for privacy reasons), and to log user assigned / withdrawn from project
+ Fixed a warning by correcting some calls to templates from managemilestone.tpl
+ Fixed the "cancel" button on the add project form to not submit the form.
+ Optimized task add form: Now in the assign field, the current user is always pre-selected, which often will save a click
+ Optimized e-mail notification when a task is added, so that the adding person does not get an e-mail
+ Added (fake) progress bar that replaces the file upload button when upload is in progress
+ Added link titles for milestone names in the project milestones view
+ Added permission check for showing the delete button for attached files in My Messages and single message view
+ Fixed reloading after deleting of attached files in My message view
+ Added alt text to the button in the project files view which takes you a level higher in the folders hierarchy
+ Fixed a notice in project messages
+ Fixed a bug in the project files lists and all message files lists: When a file is deleted, its icon now neatly fades out and is replaced by the other files moving up
+ Added new "winter" template. It is based on "standard" and provides a lighter alternative. Replaces the unmaintained "frost" template.
+ Fixed wrong image file path resulting in missing image in system message for folder added
+ Fixed wrong image file path resulting in missing image in system message for reply added
+ Added XSS protection for strings input by the user in getArrayVal()
+ Added function to edit a user's hourly rate if you are an admin
+ Updated bundled TC_PDF class to 5.9.038
+ Updated the bundled tinyMCE to 3.4.2, took alignment option out of toolbar because it seems pretty useless
+ Removed unused search modal HTML code
+ Enabled rounded borders in IE9 (CSS)
+ Corrected hard-coded string "Budget" on project dashboard to translated string
+ Added function to edit project budget
+ Optimized strings shown during hovering in several views
+ Corrected regular expression in timetracker in order to allow for single digit hours and to dismiss things like 10:60 or 25:00
+ Corrected color-coding for projects with due date in the future on dashboard
+ Removed 'Days left' from dashboard for projects without due date
+ Color-coding for projects without due dates on desktop and project administration now same as for projects with due date in the future
+ More string sanitizing in class.user.php
+ Added comments
+ Improved security in chat component (added typecast to int)
+ Corrected typo in tables optimization queries and added missing queries in update script
+ Fixed bug in files table which prevented .docx files from being stored in the database
+ New function: User is now enabled to reset his/her password when he/she forgot it
+ Added missing e-mail notification function when replying to a message
+ Added missing image files for lytebox feature
+ New translations: Slovenian, Croatian, Farsi
+ 100% completed translations: Danish, German, Greek, English, Spanish, Finnish, French, Croatian, Italian, Norwegian, Dutch, Polish, Portuguese, Brazilian Portuguese, Romanian, Russian, Serbian
+ Improved security: open .php files as plaintext only
+ Improved sorting of projects on desktop, now sorted chronologically by default
+ Improved message display: Avatar now appears next to body of text thus making better use of the given space
+ Fixed bug which prevented choosing existing project files as attachments for a reply
+ Added title for install script
+ Beautified code of several template files

Collabtive 0.6.5
+ Fixed bug when assigning tasks while email notification is deactivated / off
+ Added name of the project to the desktop calendar overlay
+ Fixed date format in calendar overlay on desktop
+ Improved translations: French, Portuguese, Czech, Brasilian Portuguese, Polished
+ Modified max no. of users to show on projects, now 10000 instead of 100
+ Remove the option "All" from the task edit form on single task view
+ Fixed a bug where a folder wouldnt be visible if visible = all was selected
+ Fixed a bug where every timetracker entry was tracked for "today" regardless of selection
+ Removed some debug output in managefile.php
+ Added check for userpermission of file editing, so the edit icon will not show up
any longer in case of missing permission
+ Added missing truncation to project title on the mymessages view
+ Corrected file->delete link for attached files in the message view
+ Backported never due for projects to the frost theme

Collabtive 0.6.4
+ Fixed a path problem with the filesize() function
+ Fixed a bug preventing Safari Users from creating tasks
+ Fixed a bug where an empty user could be assigned to a project
+ Corrected HTML Errors in project->people and project->timetracker views
+ Fixed a bug when editing a task
+ Added generic boder-radius to the CSS so all browsers that support it will display rounded borders (previously only Firefox and Webkit)
+ Removed keyboard shortcuts. they caused confusion and were probably rarely used
+ Buttons in the mainmenue now stay highlighted when an area is selected
+ Fixed a bug where users would not get an email notify when a task is assigned
+ Usernames on multiply asssigned tasks are now properly linked to each users profile
+ Fixed a problem preventing Safari and Chrome users from creating users.
+ Fixed a possible security flaw in the chat component
+ Added missing truncation to the project name in the "my tasks" column on the desktop, and the my tasks view
+ Added date of day to the timetracker PDF export per user
+ Fixed bug where no emails would be send when assigning new users to a task. Also refactored code for assigning users.
+ Fixed a possible problem in the mailer class.
+ Removed 2 unneeded tinyMCE plugins. This further reduces the amount of code to load for tiny MCE
+ Show the calendar on the desktop for all users, not just admins.
+ Updated list of languages in which the install-readme.txt is available
+ Added Swedish translation of the install-readme.txt
+ Fixed folder visibility


Collabtive 0.6.3
+ Cleaned up user profile: company only displayed if available
+ Added option "all" to visibility selection of a new folder
+ Fixed bug where display of members in project members area and user administration was restricted to 10 users
+ Removed mini calendar from sidebar since it served no real purpose
+ Fixed a bug in tasklist editing where not all active milestones were available to assign the list to.
+ Added Favicon to standard theme
+ Added TinyMCE editor options to message edit form, reply form, milestone add form, and milestone edit form
+ Dropped update support for updating from versions earlier than 0.5
+ Removed calls to deprecated function set_magic_quotes_runtime() in class tcpdf (PDF export)
+ Renamed language file folders for Chinese, Greek, Ukranian, Galician, Japanese, and Czech so they
match those used in TinyMCE
+ Complete translation to English, German, Romanian, and Bulgarian
+ Added readme in Italian
+ Added English manual
+ Added comments
+ Replaced chat icon in frost theme with a slightly darker one
+ Fixed file upload bug where file would be uploaded to the server but not to the database
+ Fixed a bug where asignee would not be set correctly upon adding a task
+ Fixed a bug where editing of a task could result in the task being assigned to no user
+ Fixed a bug where editing of a tasklist enforced assigning the list to a milestone
+ Fixed a bug where project budget would automatically be reset to 0 upon editing the project
+ Cleaned up project view: budget only displayed if > 0; description only displayed if available.
+ Cleaned up tasklist view: description only displayed if available.
+ Cleaned up message view: replies only displayed if available; removed delete icon, which did not work properly anyway.
+ Fixed a bug in email notification for task assignment
+ Fixed a bug in user timetracking filter (last day of selection not discarded any more)
+ Fixed upload paths
+ Fixed blank page when trying to install from SVN
+ Fixed problem where user with project-add-permission but without admin-permission added a project would get an error message
+ Added permission check for closing tasklist
+ Added page title for tasklist edit form, message edit form, and reply form
+ Added system message on desktop when creating, deleting, or closing a project
+ Added optimization queries for database tables 'roles' and 'roles_assigned' in update script
+ Code cleanup
@descartes
+ Fixed standard template
+ Fixed version number in the footer
+ Updated language files to match fixes
+ Fixed a bug in user management
+ Fixed typo when viewing tasklists
@whisperwind
+ Fixed minor issue where deleting user
+ Fixed an autocompletition issue where editing users
+ Fixed truncating problem where using multibyte characters
+ Added login by email in addition to login by username
+ Remove some more calls to session_is_registred in favour of isset($_SESSION)
+ Made mb_string extension mandatory during installation
+ Fixed a problem with long project/task names
@avychodil
+ Fixed wrong image path in message replies

Collabtive 0.6.2
+ Downgraded Prototype to 1.6.0.3 to avoid problems with IE.
+ Fixed a bug when filtering timetracker
+ Fixed "milestones tab unvisible for non-admins"
+ Removed property required = "0" from non-required form fields. This should improve Opera compatibility.
+ Fixed some wrong image paths.
+ Fixed a bug when editing a task.
+ Properly implemented assign task to some/all users of a project
+ Added complete russian translation
+ Fixed small display bug in single tasklist view

Collabtive 0.6.1
+ Fixed some bugs in the frost theme
+ Fixed a UTF-8 entity bug in the mailer component
+ Included missing picture for the upload progressbar
+ Removed some more calls to deprecated session_is_registered() in favor of isset($_SESSION)
+ Fixed a display Bug in Safari/Webkit
+ Fixed role editing in frost
+ Fixed a UI glitch in the login screen where to login-button would disappear onmouseover.
+ Included missing pictures for pagination arrows
+ Fixed inserting default roles fails when updating from an old version due to a missing
field
+ Fixed a bug where the calendar view would not be displayed on the project page.
+ Tasks without an end-date no longer show as a lot of days overdue
+ Fixed a bug in the formvalidator where it would not accept certain valid e-mail adresses
+ Improved Catalan translation
+ Fixed a security bug where any user could delete any file or folder in projects he belonged to.
+ Fixed editing timetracker data did not show the tinyMCE editor (mloeffen)
+ Fixed a bug in TinyMCE textfields where newlines were inserted after editing
+ File manager now stores who uploaded a file in the database. Uploader is displayed in the file list view.
+ First version of a plugin implementation
+ Fixed wrong version number in frost theme

Collabtive 0.6
+ Fixed a bug where file description of files in subfolders could not be edited.
+ Added "add project" functionality to the projects block on the desktop.
+ Fixed a bug preventing the attaching of existing files to messages.
+ Refactoring of class project. Removed a lot of unneeded code.
+ Refactoring of class tasklist. Removed a lot of unneeded code.
+ Refactoring of class message. Removed some uneeded code.
+ Refactoring of class milestone. Removed a lot of unneeded code.
+ Refactoring of class datei. Removed some unneeded code.
+ Fixed a bug in class milestone, preventing milestones with end date "today" from showing up when there where no other milestones.
+ Fixed a bug in the calculation of days left of milestones.
+ When closing or deleting stuff (tasks, milestones, messages, etc) asynchronously, the alternating background color of the table rows is properly restored.
+ Date format can now be configured to be d.m.Y or m/d/Y
+ Updated Prototype library to 1.6, Scriptaculous to 1.8., finally.
+ Fixed a bug where the filetype icon of a file would not be displayed (instead "?" icon).
+ Fixed a bug when deleting folders.
+ Fixed display of filecount when 0 files are present.
+ Implemented unlimited subfolders for files.
+ Implemented moving files between folders via drag and drop.
+ Implemented access control on a per-file basis.
+ Removed deprecated function session_register() from user::login(), now relying on $_SESSION only.
+ Implemented E-Mail notify when uploading new files
+ Tasks can now be assigned to multiple users
+ Added (fake) progress indicator when uploading files
+ Fixed a bad string replacement in install.php, preventing some users from installing
+ Fixed some MySQL queries that caused problems on some configurations (mloeffen)

Collabtive 0.5.5
+ Roles may now be edited
+ Added some missing strings (role added, edited, etc)
+ Fixed display of days left for projects without due date
+ Fixed more installer problems
+ Implemented RSS feed for project messages
+ New theme: "Frost" included. Contributed by Kemie Guaida.
+ Backported some changes to the frost theme
+ Improved themeability of some ajax elements
+ Updated PDF library to TCPDF 4.5.39
+ Removed unneeded PDF fonts, reducing the package size
+ PDF exports of messages now show the postdate of each message
+ Implemented PDF export of the "my messages" view.
+ Implemented PDF export for single messages
+ Fixed a bug where PDF export would insert empty pages between pages with content
+ More TinyMCE cleanups (unneeded packages removed)
+ Fixed some small UI glitches
+ Removed Basecamp import from the installer to reduce confusion
+ Fixed a bug where tasks could not be re-opened due to improper permissions
+ Fixed a bug where users could not be de-assigned from a project due to improper permissions
+ Users can now be assigned to projects on the admin->projects view in the project details (again).
+ Implemented email notifications when posting messages.
+ Added userpermissions for chat functionality (i.e. stop clients chatting ;) )
+ Made get methods of class milestone consistently return 10 results by default (instead of some 5, some 10)
+ Implemented simple company field in the userprofile.
+ Refactor class task to use internal method getTask() in all get methods, instead of inline code to retrieve tasks.
+ Messages are now asynchronously deleted
+ Improved Basecamp importer to use the new permissions system
+ Fixed a bug where project->tasklists would show no closed tasklists if there are no open ones
+ Added company field to the userprofile
+ Addec company field to vCard export

Collabtive 0.5
+ Fixed problem in the installer on IIS
+ Make most methods return associative arrays only , instead of numeric and associative indexed arrays.
  This creates less memory overhead, and simplifies the conversion to XML
+ First version of an XML API included
+ Improved PDF Export (full UTF8 support for PDF reports)
+ Implemented PDF export for project->messages
+ When creating a new user, the user is notified via email
+ Fixed a bug in admin->users and project->users (missing pagination)
+ Fixed some UI glitches
+ Fixed Imagelist in tinyMCE editor not displaying files without a title
+ Fixed short PHP tags in style_main.php (standard theme)
+ Fixed wrong breadcrumb link in single message view
+ Made randon number generator use mt_rand(). Numbers are attached to uploaded files.
+ Implemented new, role-based, user permissions system
+ Started porting smarty classes to strict PHP5
+ New locales: Arabian, Slovak, Swedish, Ukrainian, Finish, Catalan
+ Improved Basecamp import: Assign currently logged in user to imported projects (not just the imported users)
+ Basecamp import now imports replies to messages, as well as the messages themselves.
+ Basecamp import now properly imports task-titles , not only the textbody
+ Fixed Basecamp import in standard template (admin->system and installer)
+ Fixed a bug where userprofiles would get mangled up when changing system settings in admin->system
+ Edit project on project view now correctly shows wyswyg editor
+ Show more tasks on "my tasks" view on the desktop
+ Removed many unneeded TinyMCE Plugins from the package
+ Implemented properly styled error messages
+ Implemented Username and Password for access to RSS Feeds
+ Tasks may now be added by clicking on the day numbers on the project view calendar


Collabtive 0.4.9.1
+ Fixed display bug in mac/safari (admin->user)
+ Fixed a bug when changing the picture of users, as admin
+ Cleaned up problems in the userprofile
+ fixed bug preventing avatar pictures from being uploaded in Internet Explorer
+ Improved folder handling
+ Improved timetracker reporting (normal users can now see their own hours)
+ Folderexport now possible in the file explorer
+ Fixed a bug in timetracker report pagination (project view)
+ Fixed a bug in the JS calender on the desktop in IE
+ Fixed some wrong links in the new


Collabtive 0.4.9
+ Clear the template cache when changing themes
+ Added option Mail from name
+ Implemented ajaxified close element and delete element
+ Updated to TinyMCE 3.2
+ Fixed a bug when changing the avatar of other users, as admin
+ Implemented hourly rate setting for Users
+ Implemented Budget setting for Projects
+ Pagination now themeable
+ Implemented imagelist in TinyMCE editor. When inserting a picture, using tinyMCE a list of pictures populated from the uploaded files is presented
+ Implemented re-written JS based calendar and datepicker
+ Added chinese (simplified) localisation
+ Implemented configurable Date format
+ Fixed some security vulnerabilities
+ Fixed link to tasks RSS feed
+ Fixed detection of own URL on MS IIS
+ Added profile fields for phone and mobile to the userprofile
+ Added company information
+ Added Yahoo map to the userprofile showing the user's location using Yahoo geocoding web API
+ Implemented new calendar for  milestones on the desktop
+ Completely re-designed standard theme. Classic theme added.
+ Implemented keyboard Shortcuts (Ctrl-D,Ctrl-T,Ctrl-M,Ctrl-P,esc)
+ Timetracking report is now in ascending chronological order


Collabtive 0.4.8
+ Updated TinyMCE to 3.1
+ Messages can be attached to milestones
+ Fixed "my messages" view to include tags selection
+ Fixed "my messages" view to include tags display
+ Email alerts improved (now completely localised, available for add task and add project)
+ Support for using custom SMTP servers with Email Alerts
+ Fixed: bug in form validator -> it now accepts email adresses containing numbers
+ Improved: display of dependent items in milestones (removed unneeded comma)
+ Fixed: bug in the installer, that made timetracking unusable
+ Timezone can now be set independent of the server timezone in Admin -> System configuration
+ Cleaned up code in init.php
+ Removed redundant call to getAvailableLanguages() in init.php. -> more efficient
+ Implemented support for subfolders
+ When an administrator changes the global system language, all users language settings are updated accordingly.
+ Made link in the user profile clickable
+ Made Email in the user profile clickable
+ Fixed: bulleted lists created from the wyswyg editor (they now actually include bullets ;) )
+ Fixed: various UI glitches
+ Moved the short project report to the "description" area of the project details on projectview
+ Fixed: Only display tagcloud when there actually are tagged items in the project
+ Changed the task title to mandatory , and the text as optional
+ Added spanish readme
+ Beginngins of an XML / JSON API (class toXml)


Collabtive 0.4.7
+ Implemented tagcloud on the projectview
+ Fixed a bug in timetracker:add on windows
+ Cleaned up pathing in init.php (pointed out by jcorreia)
+ Fixed a bug in the updater, preventing messages to be posted
+ Improved installer to check for PHP 5.1 instead of only PHP5
+ Implemented OpenID login
+ Users can now be tagged
+ When deassigning a user from a project, remaining tasks of that user can be re-assigned to another user, or deleted
+ Multisite setup now possible
+ Fixed typo in JS files (character encoding = UTF8 , not :utf8)
+ Timetracking reports now include the comments
+ Implemented preliminary email alerts support
+ Alpha Version of a Google Gadget included
+ Fixed link to tasklist on My Tasks->Done Tasks
+ Updated to the latest Smarty release (2.6.19)
+ Improved Basecamp import
+ Fixed security flaw in admin.php
+ Milestones view on project->milestones can now be toggled between list and calendar view


Collabtive 0.4.6
+ Fixed a bug preventing user from logging in
+ Added dutch locale
+ Added lituanian locale
+ Added measuring of localizing completeness for each locale (translated vs untranslated ratio)
+ Language selectors now show completely localized language names ("English", "German") instead of the locale codes ("en","de")
+ Fixed display Bug in IE7 on the timetracking report (project/user)
+ When deleting a user, all timetracking for that user is deleted, too.
+ Installer cimpletely localized now
+ Additional locales supported in the installer (Spanish, Italian, Japanese, Dutch)
+ Cleaned up language files (removing redundant / unused strings)
+ Running on an SSL/HTTPS connection now properly supported
+ Fix bug when Collabtive is installed with an empty DB password
+ Fixed missing curly brace in chat.js
+ Improved protection against SQL injections
+ Implemented tagging for files and messages
+ Edit user permissions as Admin
+ Datepicker supports all supported locales now.
+ Implemented Basecamp import functionality.
+ Included Basecamp importer in the installer
+ When deleting a project, all tasks from that project are deleted too (fixed typo).
+ Fixed display bug in the "My projects" block when logged in as a non-admin user.



Collabtive 0.4.5
+ Vcard export of userprofiles
+ Fixed a bug in the milestones timeline
+ Added profile fields URL, Gender, ZIP
+ Improved Formvalidator to support regular expressions
+ Timetracker form now checks for correct time format (hh:mm)
+ Updated Tiny MCE to latest version (3.0.5) ; Solves Bug in Safari
+ Removed some unused Tiny MCE plugins from the package.
+ Improved Task management code
+ Messages can be edited again
+ Admins can now edit the passwords of all users.
+ Timetracking for Tasks now possible.
+ Project reporting can now be filtered for tasks
+ Project reporting can now be filtered for users
+ User reporting can now be filtered for projects
+ PDF Reports show the name of the project / user they were generated for
+ PDF and Excel Reports show tasks
+ Reorganized order of buttons in the projectview menu
+ Reorganized order of blocks on the desktop
+ Projectlog can be exported to excel
+ Added Accordeon in Projects Block on the desktop (shows projects description)
+ Fixed some page titles
+ Fixed security bug when uploading avatars (only pictures are accepted, now)
+ Introduced new Userrole: Client. Clients have read-only access to the system. They can also not see any internal messages.
+ When deleting a user, it can now be chosen if the tasks of this user shall be deleted or re-assigned to another user.
+ Polished edges in the installer template
+ Support for locales with more than 2 characters (like pt_br, es_gl, etc)
+ Added turkish locale
+ Added japanese locale


Collabtive 0.4
+ Closed tasks can now be edited again
+ RSS feeds are encoded in UTF8
+ Implemented search functionality (class.search.php + managesearch.php)
+ Ontype search added
+ Closed tasks are visible on the mytasks view even if they have < 1 days "left" under "closed tasks"
+ Fixed wrong link for ZIP export of projectfiles
+ Implemented add search to browser-searchbox for FF2/3 and IE7/8
+ Implemented searchplugin autodiscovery for FF2/3 and IE7/8
+ Project log can be exported to PDF
+ Progressmeter improved: The smaller part of the pie should be moving always .
+ Project progress report as PDF implemented
+ Collapsing the milestones block is now persistent throughout desktop / project view
+ Fixed "Out of range error" on INSERT queries with MySQL5 on Windows
+ Tooltips for milestone details
+ Object (Message, Task, Project, File, etc) descriptions are now properly formatted (added nl2br modifier)
+ Made state of blocks (open / collapsed) persistent for remaining (project,timetracker,log) blocks on project view
+ Improved consistency of language settings (when creating a new user, the system default language is used)
+ Page title of project view now includes Project name
+ My messages Block on the desktop shows only messages from open projects now
+ Refactored database code
+ Added stripslashes() when reading strings from MySQL
+ Added My Messages RSS Feed
+ Added RSS Autodiscovery
+ New messages can now also be added from the My Messages view
+ New Collabtive icon as favicon
+ Changed formblock toggle from appear to blind
+ Fixed notices in iCal export
+ Ical feed can now be imported to ms outlook to (outlook is a bit "special" when parsing ical)
+ Removed favicon option
+ Implemented Systemsounds for Login, Logout and Error
+ Implemented filter for Timetracker report (only display a certain timeframe). Exported reports are filtered, too.
+ Improved styling of the onlinelist
+ Fixed a bug in thumb.php when running on error_reporting(E_ALL)
+ Unified Export icon, that expands on mouseover and shows available export options (RSS , PDF, XLS , etc)
+ Implemented 154 Unit tests to test all classes against regressions automatically. We use Simpletest for this. Fixed many small bugs in the process.
+ My Messages block on the desktop only shown if there actually are messages.
+ Class documentation translated to english
+ Improved localisation in the installer, installing with other systemdefault languages than english works properly now.
+ Made Collabtive run flawless when setting error_reporting(E_STRICT) / Strict mode.
+ Improve security by making config.php non-writable again after the installer has written to it (CHMOD 0755).
+ Added confirm() when deleting closed tasklists
+ Added confirm() when deleting projects from the "my projects" view.
+ Removed project edit, and del for non-admin users on my projects view(were non-functional anyway)
+ First page of the installer better localized
+ HTML Form in installer step2 styled correctly



Collabtive 0.3.6
+ When closing a project, close any objects belonging to it, too
+ When closing a tasklist, close all tasks on the list too
+ When deleting a tasklist, delete all the tasks on the list too
+ When deleting a project, timetracking for this project is deleted too
+ ZIP Format export for projectfiles
+ Fixed uploading/attaching files when replying to a message through the single page form
+ Fixed existing file	 selector for attaching files when replying
+ Fixed closed objects view
+ Email Address now optional when editing a user
+ Various fields now only visible when present, in profile view
+ When uploading multiple files, they can now have multiple titles
+ Removed duplicated variable declarations in managetasklist.php
+ Show progressindicator only if there is at least 1 finished task
+ Make tasklist names on my tasks view clickable
+ Milestone titles in the overviews are now truncated after 30 characters
+ Added confirmdel string to french locale
+ Replying messages is possible without attaching files
+ New global JS functions delRow() (delete a table row), delEle() (delete any element), systemMsg() (fade in a block and create a timer to fadeout again)
+ Closed tasks in tasklist view are now sorted DESC (latest task shows up first)
+ Project deadline / end date can now be entered
+ Project view shows remaining days until deadline, instead of startdate
+ Fixed problem with file upload paths (http://www.collabtive.o-dyn.de/forum/viewtopic.php?f=11&t=80)
+ PHP Scripts are now uploaded as Textfiles. This prevents random script execution and enables easy viewing as text
+ Duplicate email address / username results in an errorpage (not in a blank page)
+ Removed a duplicated Constant definition in install.php
+ Fixed page title in userprofile view to be multilanguage
+ Pagetitles now finally _completely_ localized
+ Fixed Default system locale->user locale relation



Collabtive 0.3.5
+ Add Flash progressmeter on project view
+ Attach files when replying a message
+ Show replies only when there are > 0 replies in the message view
+ All my Messages view
+ Eventmessages are faded out after 7 seconds
+ Correctly display lightbox on filelinks in the single message view
+ Large code cleanup (no more E_NOTICE)
+ Fixed datepicker when using english locale
+ Add pagination at the project->files view
+ Add projects of a user block to the userprofile , for admins
+ Fixed task title truncating on desktop
+ Updated update.php to reflect changes in 0.3.5
+ Added simple timetracking
+ Changed Profile link in the main navigation from edit profile , to view profile
+ Current time can now be auto entered in the timetracker form onclick.
+ User password can now be changed
+ Activity log is now paginated
+ Excel export for timetracker
+ PDF export for timetracker
+ Fixed pagination to not always "remember" the last page visited. Caused problems when previously visited page doesn't exist anymore.
+ Fixed a 4545possible security vulnerability in class.datei.php
+ Fixed localisation for eventmessages in the filemanager
+ Added a Javascript confirm popup to all delete actions, to avoid accidential deletes
+ Added a Timetracking Tab in the projectview
+ Put all strings from MySQL through stripslashes() to reverse mysql_real_escape_string on add
+ Installer checks for templates_c to be present and writable at startup
+ Installer has better errorhandling
+ Added danish locale