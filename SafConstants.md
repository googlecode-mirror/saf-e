# Introduction #

SAF Defines a number of constants in the global scope. Contants fall into the following categories:

  * **Optional** Constants can be defined in localize.php
  * **DefineLoad** Contstants can be auto-loaded from dot files when present
    * Any DefineLoad Constant can be overridden in the localize.php when present (localize.php trumps the dotfile)
    * DefineLoad Constants always have a fallback default defined in the code
  * **Defined** Constants are code controlled, generally static, and generally should not be changed
  * **Derived** Constants are code controlled, generally dynamic, and should not be changed

## DefineLoad Constants ##

  * APPLICATION\_ENV - Defaults to "production" - Indicates which configuration profile to load
  * APPLICATION\_CONF - Defaults to APPLICATION\_PATH/configs/application.xml - Fully qualified path to the configuration file
  * APPLICATION\_STATUS - Defaults to "online" - Indicates the application's current state (online|offline|maintenance|install)
  * APPLICATION\_RESPONSE\_FORMAT - Defaults to "html" - The output format the application should prefer in _emergency cases_ when it is unable to detect what the appropriate output should be.
  * APPLICATION\_EXCEPTION\_MESSAGE - Defaults to "Please inform your support staff" - The default message to include on any exception lacking essential details.
  * APPLICATION\_BASE\_URL - Defaults to an auto-detected value - The URL for the root of the application
  * APPLICATION\_STANDARD\_PORT - Defaults to 80 - The HTTP port for the APPLICATION\_BASE\_URL
  * APPLICATION\_SSL\_PORT - Defaults to 443 - The HTTPS port for the APPLICATION\_BASE\_URL when using SSL
  * ZEND\_PATH - Defaults to the empty string - The fully qualified path to find the Zend Framework library. If left empty, it is assumed that ZF is already in the path.

## Defined Contants ##

## Derived Contants ##

  * APPLICATION\_PATH - The fully qualified path to the /application/ folder.
  * APPLICATION\_LIB\_PATH - The fully qualified path to the /library/ folder.
  * APPLICATION\_SSL - Boolean value indicating whether SSL is supported
  * APPLICATION\_PROTOCOL - The HTTP protocol to use when generating URLs referring to the application
  * APPLICATION\_START\_TIME - The timestamp of when the application started

## Optional Contants ##

  * APPLICATION\_PUBLIC\_PATH - The fully qualified path to the /public/ folder. 99% of the time this can be safely auto-detected.
  * APPLICATION\_INSTALL\_PATH - The fully qualified path to the parent directory of /library/ and  /application/ . 99% of the time this can be safely auto-detected.
  * ZEND\_REQUIRED - Defaults to false - Halts the bootstrap if Zend Framework is not found

## Special Contants ##

  * APPLICATION\_ROUTER\_NAME - How the application knows the root resource that is being requested in a Apache-Multiviews setup. [see also: Router Files](RouterFiles.md)