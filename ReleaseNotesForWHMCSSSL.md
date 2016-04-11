### Version 1.5 ###
_Released on Dec 16, 2013_

  * Multi-Domain Certificates support added
  * Fixed bug causing incorrect display of list of certificates in addon for cases when production username is same as sandbox one.
  * Fixed showing all possible Management options in user area instead of showing only available ones.
  * Fixed of issue with no fields appearing in ‘Module Settings’ after selecting ‘namecheapssl’ from dropdown menu.
  * Fixed issue with "Unhandled Exception" error being received while reissue
  * Minor internal fixes.

### Version 1.4.2 ###
_Released on Nov 15, 2013_

  * Fixed bug related to ‘Invalid Link Followed’ error (Addon updated to version 1.3)

### Version 1.4.1 ###
_Released on Nov 1, 2013_

  * Added possibility to reissue Symantec certificates from WHMCS interface.
    * Added possibility to use HTTP-based validation instead of approval email.
    * Added possibility to download certificate from WHMCS user area.
    * Added additional checks for API responses.
    * Added Whois emails to list of addresses for Domain Control Validation.
    * Fixed uninformative error message ‘Invalid Phone or Country code’.
    * Fixed dependence of module language upon language choice in WHMCS
    * Minor fixes.

### Version 1.4.0 ###
_Released on Sep 27, 2013_

  * Improved log functionality
  * Added possibility to link/relink Namecheap certificates (existing) with WHMCS orders.
  * Added built-in lookup for list of certs for all of users having products set up within WHMCS module.
  * Added compatibility with Comodo Sandbox Environment
  * Added daily email report for all actions with Namecheap SSL Module.
  * Reduced amount of hard-coded lang variables for better translatability
  * Minor fixes

### Version 1.3.2 ###
_Released on Jul 04, 2013_

  * Fixed minor file issue of version 1.3.1.

### Version 1.3.1 ###
_Released on Jul 04, 2013_

  * Changed installation process.
  * Changed certificate creation process. Now the NC side certificate is created on the third step of configuration.
    * The created Certificate’s used for backward compatibility with the presence of certificate NC REMOTE ID in database.
  * If the product settings of the ordered Certificate have "Use existing SSL from account" option enabled, then on the third step of configuration all the certificates with the "new purchase" status will be verified. If there is an Active certificate of the same type a REMOTE ID will be used and a new certificate will not be created.
    * For PositiveSSL certificates type of "PositiveSSL Free" is checked.
  * Added Thawte certificates support.
  * Added necessary additional fields Comodo EV SSL, Comodo EV SGC SSL certificates on the first configuration step.
  * Added necessary additional fields for the following Certificates: GEOTRUST: True BusinessID With EV, True BusinessID, True BusinessID Wildcard; VERISIGN: Secure Site, Secure Site Pro, Secure Site with EV, Secure Site Pro with EV; THAWTE: SSL123, SSL Web Server, SGC Super Certs, SSL WebServer EV

**Bug Fixes:**

  * Fixed a case where the php.ini directive arg\_separator.input not equal to "&".
  * Removed extra check for null value phone / fax number on the side of the module.
  * Fixed the hook to synchronize the date and state of expiration and reissue
  * Fixed possible php parse error in addon. Could take place previously when php.ini directive short\_open\_tag was disabled.


### Version 1.3.0 ###
_Released on Jun 20, 2013_

  * $1.99 PositiveSSL certificates can now be used for activation from WHMCS with ‘Use existing SSL from account’ feature.
  * Fixed possible issues with viewing information and synchronizing due dates from admin area.
  * Fixed possible source of ‘memory’ issue occurring while first access to Namecheap addon.
  * Changed installation directories – now addon is located in ‘addons’ folder, not in ‘admin’ .
### Version 1.2.6 ###
_Released on Oct 25, 2012_

  * Products/Services Configuration bug fixed.
  * Callback details for DV SSLs bug fixed.

### Version 1.2.4 ###
_Released on Oct 21, 2012_

  * "Use existing SSL from account" bug related to absence of eligible products fixed.

### Version 1.2.3 ###
_Released on Oct 13, 2012_

  * Renewal bug related to error 2011300 fixed.

  * "Use existing SSL from account" bug related to mismatch of product names fixed.

### Version 1.2.2 ###
_Released on Aug 20, 2012_

  * Installation mechanism improved.

  * Database related error during installation fixed.

  * New 'Callback Contact Fields' added for organization validation comodo certificates.


### Version 1.2.1 ###
_Released on Apr 8, 2012_

  * Additional compatibility with WHMCS 5.x version added.

### Version 1.2 ###
_Released on Mar 30, 2012_

  * Reissue functionality for Comodo SSL Certificates
  * Synchronize due date and reissue state functionality
  * View certificate details (including Namecheap Order ID and Certificate ID)
  * Debug Mode for troubleshooting issues (log Namecheap API events)


### Version 1.1.5 ###
_Released on Dec 22, 2011_

  * Compatibility with the latest Symantec API for Organization and Extended validation added.

### Version 1.1.4 ###
_Released on Sep 8, 2011_

  * Maintenance Release
  * Multilanguage support added
  * Automatic renewal functionality enabled
  * “Activation Expiration” compatibility added for “$1.99 upgraded” Free PositiveSSL certs.
  * Compatibility with New Namecheap API added
  * “Tech Organization Name” field added to Technical Contact details
  * Welcome/configuration email sending control functionality added

### Version 1.1.3 ###
_Released on Aug 1, 2011_

  * The list of available SSL Certificates is automatically synchronized with Namecheap.com
  * Compatibility with the latest version of WHMCS (4.5.2) added
  * Customization options for “Technical Contact Details” added
  * SSL Certificate Validity Period configuration process changed. Now validity period is set based on the billing cycle

### Version 1.1.2 ###
_Released on May 28, 2011_

  * Bug Fix: Use existing SSL from account bug fixed.

### Version 1.1.0 ###
_Released on Jan 21, 2011_

  * Support for VeriSign Secure Site, VeriSign Secure Site Pro, VeriSign Secure Site EV, VeriSign Secure Site Pro EV, Geotrust TrueBusinessID and Geotrust TrueBusinessID WildCard certificates.

  * Initial Release

### Version 1.0.0 ###
_Released on Nov 07, 2010_

  * Initial Release