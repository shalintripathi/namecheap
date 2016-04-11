# Namecheap.com WHMCS SSL Module (v 1.5) #


---

**Note:**_This version is fully compatible with 5.2.x versions of WHMCS._

---

### Updated on Dec 16, 2013 to Version 1.5 ###
  * Multi-Domain Certificates support added
  * Fixed bug causing incorrect display of list of certificates in addon for cases when production username is same as sandbox one.
  * Fixed showing all possible Management options in user area instead of showing only available ones.
  * Fixed of issue with no fields appearing in ‘Module Settings’ after selecting ‘namecheapssl’ from dropdown menu.
  * Fixed issue with "Unhandled Exception" error being received while reissue
  * Minor internal fixes.

[Release Notes](http://code.google.com/p/namecheap/wiki/ReleaseNotesForWHMCSSSL)

### Before you begin ###

Namecheap.com SSL module for WHMCS is an open-source plugin that is distributed free of charge. This module allows you to automate SSL Certificate sales with the Namecheap platform.

#### Pre-requisites ####
  * Access to WHMCS admin area.
  * An understanding of [Namecheap’s environments](http://www.namecheap.com/support/api/api.aspx).
  * Namecheap account with API access enabled on the desired environment.

#### List of supported SSL certificates: ####

You will be allowed to resell all of our SSL products:

**GeoTrust Cerificates:**

  * RapidSSL
  * RapidSSL Wildcard
  * GeoTrust QuickSSL
  * GeoTrust QuickSSL Premium
  * GeoTrust True BusinessID with EV
  * GeoTrust TrueBusinessID
  * GeoTrust TrueBusinessID WildCard
  * GeoTrust TrueBusinessID Multi Domain
  * GeoTrust TrueBusinessID with EV Multi Domain

**Comodo Certificates:**

  * Comodo PositiveSSL
  * Comodo PositiveSSL Wildcard
  * Comodo InstantSSL
  * Comodo InstantSSL Pro
  * Comodo PremiumSSL
  * Comodo PremiumSSL Wildcard
  * Comodo EssentialSSL
  * Comodo EssentialSSL Wildcard
  * Comodo EV SSL
  * Comodo EV SGC SSL
  * Comodo Unified Communications
  * Comodo PositiveSSL Multi Domain


**VeriSign Certificates:**

  * VeriSign Secure Site
  * VeriSign Secure Site Pro
  * VeriSign Secure Site EV
  * VeriSign Secure Site Pro EV

**Thawte Certificates:**

  * SSL 123
  * Web Server
  * Web Server EV
  * Supercert


---

**Important Note:**

_You may find ComodoSSL in the list of SSLs during setting up products in WHMCS. ComodoSSL is a test product, it is included in the list of products, but it is not fully supported yet. Please do not set up ComodoSSL Products._


---



### Sandbox and Production Environments ###

Namecheap has a production as well as a test server environment. The test server environment is called Sandbox. We urge you to test the module in our [sandbox environment](http://www.sandbox.namecheap.com/), before pointing it to production. It uses same calls as our production environment except that you will not receive actual SSL product in the end of the process and will not be charged real money. Difference between setting product for Sandbox and for production will be described in "Setting up products and pricings" section.

#### List of certificates supported in Sandbox: ####

All of our certificates are supported in sandbox:


**GeoTrust Cerificates:**
  * RapidSSL
  * RapidSSL Wildcard
  * GeoTrust QuickSSL
  * GeoTrust QuickSSL Premium
  * GeoTrust True BusinessID with EV
  * GeoTrust TrueBusinessID
  * GeoTrust TrueBusinessID WildCard
  * GeoTrust TrueBusinessID Multi Domain
  * GeoTrust TrueBusinessID with EV Multi Domain


**VeriSign Certificates:**
  * VeriSign Secure Site
  * VeriSign Secure Site Pro
  * VeriSign Secure Site EV
  * VeriSign Secure Site Pro EV

**Thawte Certificates:**
  * SSL 123
  * Web Server
  * Web Server EV

**Comodo Certificates:**
  * Comodo PositiveSSL
  * Comodo PositiveSSL Wildcard
  * Comodo InstantSSL
  * Comodo InstantSSL Pro
  * Comodo PremiumSSL
  * Comodo PremiumSSL Wildcard
  * Comodo EssentialSSL
  * Comodo EssentialSSL Wildcard
  * Comodo Unified Communications
  * Comodo PositiveSSL Multi Domain



---

**Important Note:**

Please note that activation of Comodo OV and EV certificates will not lead to receiving test certificate itself, only DCV email will be sent.


---


### Download and installation ###

Installation of our SSLmodule is very simple and takes just a few minutes:

1. Download and extract attached archive. It can be downloaded here: https://code.google.com/p/namecheap/downloads/list.  Copy the contents to the root folder of whmcs (folder structure will remain the same).

2. Go to 'Setup >Addon Modules' in your WHMCS Admin area and activate the addon. Then go here:

![http://files.namecheap.com/images/googlecode/ssl-module-addon-installation.png](http://files.namecheap.com/images/googlecode/ssl-module-addon-installation.png)

The SSL Module Addon installation is now complete.

---

Important Note:

If you receive any errors or cannot access addon please set up access permissions to addon for everyone as on screenshot:

![http://files.namecheap.com/images/googlecode/Access%20Rights.png](http://files.namecheap.com/images/googlecode/Access%20Rights.png)


---

### Setting up products and pricings ###

To setup an SSL certificate product, please follow the steps below:

1. Create a new product within your WHMCS.

2. Ensure the welcome email is set to "None" in the dropdown menu on the Details tab, as the module sends its own email.

3. In this version, the module billing cycles and SSL validity period are configured via standard WHMCS “Products/Services” settings. To access this, go to the Pricing tab and select Payment Type to Recurring. Now disable _“One Time/Monthly”_, _“Quarterly”_ and _“Semi-Annualy”_ billing cycles since they are not applicable to SSL Certificates. Finally, specify prices for remaining billing cycles. _“Annually”_ corresponds to 1 year of SSL certificate validity (i.e. the SSL will be registered for 1 year). Biennially and triennially refer to 2 and 3 years respectively.

![http://files.namecheap.com/images/googlecode/Product-Settings.png](http://files.namecheap.com/images/googlecode/Product-Settings.png)


4. On the _Module Settings_ tab, choose _"Namecheapssl"_ from Module Name dropdown menu.

5. Enter your API credentials. If you wish to test this module in sandbox environment, make sure to enter your sandbox username, sandbox API key in the corresponding text fields. Also, be sure to check the _“Test Mode”_ box.

6. Choose the certificate type from the drop-down menu.

7. If you have a special _“Promotion Code”_, type it into the corresponding text field.

8. If _“Use existing SSL from account”_ option is checked we will try to use an existing SSL certificate of this type from your Namecheap account first. If there is no SSL available that can be used, a new certificate will be purchased.

9. The purpose of the next set of fields is to customize the Technical Contact Details for any purchased SSL Certificates (fields are shown on a screens shot below). By default, Namecheap Contact details are used (email address sslsupport@namecheap.com). Using a custom Technical Contact Details is useful for resellers who wish to appear as an independent business entity to their customers. Depending on whether you want to use custom Technical Contact Details or not, perform the corresponding action:
  * In order to use **Default Technical Email** leave ALL of the fields below empty.
  * If you wish to use **Custom Technical Email** fill in ALL of the fields below.

![http://files.namecheap.com/images/googlecode/Customizing-TechnicalContacts.png](http://files.namecheap.com/images/googlecode/Customizing-TechnicalContacts.png)

Note: Our ability to provide support to customers who use custom Technical Contact Fields is limited. In case custom technical contact details are used, we cannot perform reissues, resending of approver email/ certificate, or cancellation/revocation of GeoTrust and VeriSign SSL Certificates. However, since you possess control over technical contact, you can access GeoTrust/VeriSign Live Account and perform these required actions yourself.

For control of GeoTrust SSLs, please visit: https://products.geotrust.com/orders/orderinformation/authentication.do

For control of VeriSign SSLs, please visit: https://products.verisign.com/orders/orderinformation/authentication.do

**Order Process**

The product will appear in the order process as a regular product which can be added to the cart. No configuration is performed before purchase. Once a certificate is purchased, paid for, and activated, the user is sent an email containing a link which takes them to configure the certificate in the client area. Once all details have been provided, the configuration data is sent to the Certificate Authority for validation. No manual intervention is required from you.

You have an option to resend an email containing a link to the certificate configuration page to the client. This page is also accessible from the client area (My Products & Services -> Product Details -> View Certificate Details). Options to resend approver email and email with the certificate issued are also available in the client area.

**Welcome/Configuration Email**

On its first launch, Namecheap SSL module automatically creates a configuration email template (see “SSL Certificate Configuration Required” in section "Product Messages" of Email Templates in Setup). It contains link to activation process inside your client area for a specific SSL certificate.

Sending of SSL Configuration Email is controlled by the following parameters:

Type of product setup behavior in Module Settings tab:

![http://files.namecheap.com/images/googlecode/Module-Settings.png](http://files.namecheap.com/images/googlecode/Module-Settings.png)


1. Configuration email is always sent for options “Automatically setup the product as soon as an order is placed” and “Automatically setup the product as soon as the first payment is received”. If you select “Automatically setup the product as soon as an order is placed”, a configuration email will only be sent if the order is placed from the client area. The module itself will run only if you place the order from client area as well.

2. If the options “Automatically setup the product when you manually accept a pending order” or “Do not automatically setup this product” are selected, then sending of the Configuration Email will depend on the box “Send Welcome Email”:

![http://files.namecheap.com/images/googlecode/Welcome-Email-Setting.png](http://files.namecheap.com/images/googlecode/Welcome-Email-Setting.png)


You can modify content of the configuration email at any time.

### Activation from WHMCS ###

In order to activate a certificate purchased from you, your client needs to access list of your services and click on ‘View Details’ button next to ordered certificate.

![http://files.namecheap.com/images/googlecode/View-Certificate-Details.png](http://files.namecheap.com/images/googlecode/View-Certificate-Details.png)


After that your client needs to click ‘View certificate details’ and ‘Configure certificate’.

He will see window with SSL activation fields:

![http://files.namecheap.com/images/googlecode/Configuring-SSL-Certificate.png](http://files.namecheap.com/images/googlecode/Configuring-SSL-Certificate.png)

At this stage your client needs to input CSR code (obtained from web-server), select web-server type and fill in valid admin contact info.

Basically admin contact info is to be pre-filled from user's WHMCS profile.

Then your customer clicks 'Proceed' and gets to next step.

In case CSR code is ok, your client will see the list of available DCV options on the next page.Those DCV options are basically HTTP-based validation or approval email. Your client may select any of emails there to receive Domain Control Validation email on that address or select HTTP-based DCV. In case HTTP-based DCV radiobutton is selected no email is to be sent for validation, however your customer will need to submit a specific file to root folder of his domain.
Name and contents of file will be shown after he clicks ‘Submit’ and activation data gets transmitted to Certificate Authority. Also the file contents can be checked in customer’s area by viewing information of certificate that is being activated.

Further activation process is between you or your customer and Certificate Authority. You are to receive approval email (for most certificates except Symantec OV and EV certs) and to approve it. After that certificate is to be sent to you (within 10-15 mins) or some docs request is to be sent to you for OV or EV certs.


---

**Important Note:**

Language variables containing strings with instructions to HTTP-based validation and with file contents are stored in /modules/servers/namecheapssl/lang/English.php. If you are using other language you need to create
/modules/servers/namecheapssl/lang/%yourlanguage%.php and change values of the following variables to corresponding phrases in your language: $_MOD\_LANG['ncssl\_http\_based\_validation'] ,$_MOD\_LANG['ncssl\_show\_validation\_file\_contents'] , $_MOD\_LANG['ncssl\_custom\_phrase\_sslcertapproveremaildetails'],$_MOD\_LANG['ncssl\_custom\_phrase\_sslconfigcompletedetails']

---


### Debugging and Addon functions ###

Our Namecheap SSL Module addon has the following functions:
  * Log
  * Link/Re-Link WHMCS cert ID to NC Cert ID
  * Certificate list

Log

During setting up product you may check ‘Debug mode’ box in order to have your actions with module logged :

![http://files.namecheap.com/images/googlecode/Enabling-Log.png](http://files.namecheap.com/images/googlecode/Enabling-Log.png)

This will allow you to check log of actions performed by module in addons section in WHMCS:

There you will find all of the actions performed by your customer with namecheapssl products, all hook actions and all API calls and responses. This is very convenient for investigation of possible issues.

Each action will have WHMCS service ID of certificate that was viewed/activated/reissued from WHMCS user area so you will be able to track actions of your customers.

**Link/Re-Link WHMCS Cert ID to NC Cert ID**

This feature allows connecting WHMCS certificate record to existing Namecheap certificate.

For this you will need to input WHMCS invoice ID given after order placement to corresponding box and then to input certID of an existing certificate within your NC account (can be found next to certificate in list of SSLs at Namecheap).

After clicking ‘Sync’ details for specific certificate in your WHMCS will be taken from Namecheap.


**Certificate List**

In this section you may see all of the certificates ordered via this WHMCS from all of the NC accounts associated with it.

You will see the following fields in the lists:

![http://files.namecheap.com/images/googlecode/Certificate-list.png](http://files.namecheap.com/images/googlecode/Certificate-list.png)


### Reissue and renewal ###

Reissue and renewal are 2 different actions with SSL certificate.

After the certificate gets issued, it's status becomes ‘active’ and you will see the following screen while viewing it’s info:

![http://files.namecheap.com/images/googlecode/Reissuing-Cerificate.png](http://files.namecheap.com/images/googlecode/Reissuing-Cerificate.png)

There you may download certificate in zip archive in corresponding format for your web-server or reissue the certificate.

**Reissue**

Reissue is the process of having certificate regenerated with Certificate Authority if needed. For example, if your client has lost your Private Key. For that he needs to view details of your certificate from list of certificates in WHMCS user area and click ‘Reissue Certificate’ button:

Further process will be very similar to activation – your customer will need to paste CSR for the same domain name and select approval email. Reissuing a certificate will change its Namecheap Certificate ID. A new certificate record will be added to your Namecheap account.

**Due date and reissue state synchronization**

All changes done in WHMCS are synchronized with your Namecheap account automatically once a day (when WHMCS cron runs). Also you can perform manual synchronization any time by clicking ‘Synchronize with Namecheap’. This will set WHMCS due dates and reissue states in sync with Namecheap admin area when needed:

![http://files.namecheap.com/images/googlecode/Sync-duedate-reissuestatus.png](http://files.namecheap.com/images/googlecode/Sync-duedate-reissuestatus.png)

**Renewal** is pretty much the same as purchasing new certificate with Namecheap. Renewal functionality is fully integrated into the module. As long as you have “Payment Type” set to “Recurring” when creating a product, invoices for renewals will be generated automatically. Once paid, renewal SSLs will be created automatically as well. Please keep in mind that after the renewal SSL is created, it still requires activation using [CSR](http://namecheap.simplekb.com/kb.show?show=article&articleid=817&categoryid=71).

### Multi-Domain Certificates ###

**General information about product**

Recently Multi-Domain Certificates were added to Namecheap’s product list. These certificates are quite popular among customers, but require some additional configurations. during
Multidomain certificates can be divided into 2 categories – old single domain products that now support additional domains as a configurable addon, and new multi-domain products that come with a predefined number of domains included in the product by default (more domains can be included additionally as well). Therefore number of domains included by default differs across the products. See the table for details:

|<b>Provider</b>|<b>Product name</b>|<b>Default number of domains<br /> (domain from CSR is counted here)</b>|<b>Maximum number of domains</b>|<b>Maximum number of domains<br /> that should be used in configurable options</b>|
|:--------------|:------------------|:-----------------------------------------------------------------------|:-------------------------------|:---------------------------------------------------------------------------------|
|Comodo         |PositiveSSL Multi-domain|3                                                                       |100                             |97                                                                                |
|Comodo         |Unified Communications|3                                                                       |100                             |97                                                                                |
|Geotrust       |QuickSSL Premium   |1                                                                       |4                               |-                                                                                 |
|Geotrust       |True Business ID with EV Multi-domain|5                                                                       |25                              |20                                                                                |
|Geotrust       |True Business ID Multi-domain|5                                                                       |25                              |20                                                                                |
|Thawte         |SSL Web Server     |1                                                                       |25                              |24                                                                                |
|Thawte         |SSL Web Server with EV|1                                                                       |25                              |24                                                                                |
|Thawte         |SGC Supercerts     |1                                                                       |25                              |24                                                                                |
|Verisign       |Secure Site Pro with EV|1                                                                       |25                              |24                                                                                |
|Verisign       |Secure Site with EV|1                                                                       |25                              |24                                                                                |
|Verisign       |Secure Site        |1                                                                       |25                              |24                                                                                |
|Verisign       |Secure Site Pro    |1                                                                       |25                              |24                                                                                |

**Setting up Multi-Domain Certificates**

First of all, you need to set up product as described in ‘Setting up products and pricings’ section.  After product is set up the default number of addon domains (from table above) will be available during activation.
In order to give your customers ability to order additional domains you need to set up configurable options for each multi-domain certificate you set up. It would not take much time.

1. Go to configurable options and click on ‘Create a new group’ there.


![http://files.namecheap.com/images/googlecode/setting-up-multi-domain.png](http://files.namecheap.com/images/googlecode/setting-up-multi-domain.png)

2. Fill in the name of your group (We recommend mentioning product name there) and select a product you wish to associate the configurable option with.

![http://files.namecheap.com/images/googlecode/configurable-option-groups.png](http://files.namecheap.com/images/googlecode/configurable-option-groups.png)

3. Click ‘Add new configurable option’ button.

![http://files.namecheap.com/images/googlecode/adding-configurable-options.png](http://files.namecheap.com/images/googlecode/adding-configurable-options.png)

4. Option Name. This field consists of two parts, the first one is internal and the other one is Visible to clients. Option name must contain ‘san|’ element. The text input after “|” will be displayed in your clients’ shopping cart.   We recommend  to specify default number of addon domains that are already included in certificate (For example – “san|Addon domains ( 3 domains are included by default)” for PositiveSSL MultiDomain.

5. Select ‘Quantity’ as Option Type from dropdown menu. Click ‘Save changes’.

6. Type 0 in ‘Minimum Quantity Required’ and the value from the last column of the table above as ‘Maximum Allowed’. For example, if you are setting up PositiveSSL Multi Domain, please input 97 as maximum.

7. Use any name (it will not be shown anywhere) in the box next to ‘Add Option:’ and click ‘Save changes’.

8. At this point you will see the table for pricing similar to one you’ve filled in during setting up product. Please fill in pricing for each additional domain for different terms.

9. Click ‘Save changes’

![http://files.namecheap.com/images/googlecode/adding-configurable-options.png](http://files.namecheap.com/images/googlecode/adding-configurable-options.png)


That’s it. Now if your customer orders a multi-domain certificate he will be able to add some additional domains to his order.



---

**Important Note:**

Please mention the default number of domains provided with Multi-Domain Certificates in product name or product description – this will guarantee your customers that even if they do not order any additional domains, they will have some of them added by default.

---


### QuickSSL Premium multi-domain setup ###

As you could see from the table above, QuickSSLs Premium are also multi-domain product from now on. However they have certain specifics.

  * You have 2 options during purchasing QuickSSL Premium – default single-domain option or option with 4 additional subdomains.

  * You may only add subdomains of different levels as addons – different domains will return error.

  * Price remains the same in case you activate QuickSSL Premium with 1 or 4 additional subdomains.

Configurable option for QuickSSL Premium is a bit different. Please follow the next steps in order to configure it.

![http://files.namecheap.com/images/googlecode/quickssl-configurable-options.png](http://files.namecheap.com/images/googlecode/quickssl-configurable-options.png)

1. Please select Option type as ‘Dropdown’.

2. Please set name as ‘san|Addon Subdomains’ (or, as for other Multi-Domain Certificates, any other phrase after ‘|’.

3. Fill the field below ‘Options’ with “0|No addon subdomains” (or any other phrase after ‘|’ on your demand. “0” is the keyword meaning that selecting this option will create no fields for client during activation.

4. Click ‘Save Changes’.

5. Fill the new field with ‘1|4 addon subdomains’ (or any other phrase after ‘|’ on your demand). “1” is the keyword meaning that selecting this option will create 4 fields for addon subdomains for client during activation.

6. Click ‘Save changes’.


Example of configurable options table:

![http://files.namecheap.com/images/googlecode/quickssl-configurable-options-example.png](http://files.namecheap.com/images/googlecode/quickssl-configurable-options-example.png)

### Managing addon domains after purchase is made ###

Your client as well as you will be able to add more domains to a certificate after order is complete.

This can be done either from user and admin areas.

In order to do that in admin area, your customer needs to mouse over ‘Management Actions’ and select ‘Upgrade/Downgrade Options’.


![http://files.namecheap.com/images/googlecode/managing-add-ons-after-purchase.png](http://files.namecheap.com/images/googlecode/managing-add-ons-after-purchase.png)

There your customer can increase number of addon domains. An attempt to decrease that number will cause error. A new hook was implemented in client area tracking attempts to decrease number of addon domains.


---

**Important Note:**

The number of addon domains can be changed from client area only after invoice for order is paid.

---



In order to change number of addon domains in WHMCS admin area, you need to access product page and manually input the new number of addon domains.

Please note that in case you decrease or increase this number here, you need to invoice/refund your client manually.

![http://files.namecheap.com/images/googlecode/editing-add-ons.png](http://files.namecheap.com/images/googlecode/editing-add-ons.png)


---

**Important Note:**

In case you or your client increases number of addon domains for a certificate your Namecheap account will be charged for every extra addon domain used during activation/reissue.

---


For example, if your customer has ordered 2 more domains before reissue or you have manually increased number of addon domains by 2, your Namecheap account will be charged for 2 addon domains after reissue is complete from WHMCS client area.

### Activation of Multi-Domain Certificates ###

Activation process is similar to activation of single-domain certificates. Below the CSR box you will see fields for additional domains (or subdomains in case of QuickSSL Premium).

It is not strongly required to fill in all the Addon Domain field during the first activation. Duplicate records are not allowed (including duplicates in CSR’s common name and addon domain fields).

Below is an example of first configuration page for PositiveSSL Multi Domain with 5 addon domains ordered (1 domain from CSR + 2 addon domains by default + 5 addon domains ordered separately).

![http://files.namecheap.com/images/googlecode/multi-domain-activation.png](http://files.namecheap.com/images/googlecode/multi-domain-activation.png)

The list of approver emails is different from the one you see on the second configuration page for single-domain certificates. It contains only local parts of email addresses that can be used for domain control validation. Once your customer selects one of the local parts, it will be added to every domain/subdomain input in Addon domains fields.

![http://files.namecheap.com/images/googlecode/multi-domain-approver-email.png](http://files.namecheap.com/images/googlecode/multi-domain-approver-email.png)

For example, if he selects “admin@” as approver email having “domain.com” as common name in CSR and “secure.domain.com” and “domain2.com” as addon domains, the approvals will be sent to admin@domain.com, admin@secure.domain.com and admin@domain2.com .

If your customer wishes to change email for one of the domains, he should contact you, and you in turn need to contact us via live chat or ticket system to have emails changed.

Such approver email selection flow on second configuration page is caused by certain limitations in WHMCS core.


### FAQ ###

**Q:** I cancel certificate and nothing happens

**A:** Cancellation is being performed only in your WHMCS, but not in our system. Please submit a cancellation request with our SSL support team for certificate to be revoked and refunded


**Q:** Does your module have multi-language support?

**A:** Yes, multi-language is fully integrated with WHMCS so you may change the default language of your WHMCS and language will be changed for fields used in module as well. Please note that you will need to create a custom %yourlanguage%.php file in lang directory at modules/servers/namecheapssl/lang for some fields to be translated as well. You may use default English.php as translation template.

**Q:** Getting “ _[2010167](2010167.md)_ Parameter Years is Missing” error while accepting order.

**A:** This error usually occurs when Pricing is set up improperly for your SSL product. Please doublecheck that Payment type is set to ‘Recurring’ and there is ‘-1’ input in ‘Monhtly, Quarterly, and Semi-Anually’ fields to disable possibility of ordering SSL for terms less than a year as SSL certificates can only be ordered and issued for a whole number of years only.

**Q:** I am receiving ''['" or any other strange characters instead or error messages while activation of my renewal certificate

**A:** This is a known bug, our developers are currently investigating it. In case you face this issue please email details to sslsupport@namecheap.com and kindly purchase and activate renewal certificate manually from Namecheap if renewal is urgent. After purchasing certificate manually you will need to sync the IDs using  ‘Link/Re-Link WHMCS Cert ID to NC Cert ID’  addon function.