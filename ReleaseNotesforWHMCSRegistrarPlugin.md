#### Version 1.2.7 for WHMCS 5 ####
_(Release Date: Oct 22, 2013)_

  * Added .fr, .sg, .com.sg, .fr, .net.au, .org.au, .com.au, .es, .com.es, .nom.es, .org.es support
  * Removed error "Domain name not found" for domains in any status, except for not in "Active" or "Expired"
  * Added "Job Title" additional field for .ca and .au domains
  * All errors from API response are returned by the module (in case there is more than one error)
  * Fixed error with domains that have been added in punycode to WHMCS
  * Added conversion for registrant state/province and zip code fields for .ca domains according to the registry requirements


#### Version 1.2.6 for WHMCS 5 ####
_(Release Date: May 10, 2013)_

  * Added IDN support
  * Added debug mode
  * Removed validation for empty phone/fax fields
  * Fixed bug for editing MX and MXE records
  * Fixed bug for setting default nameservers after domain registration
  * Changed 4 default NS count to 5
  * Fixed dependency on php directive arg\_separator.output

#### Version 1.2.5 for WHMCS 5 ####
_(Release Date: Dec 14, 2012)_

  * Added logs on exceptions

#### Version 1.1.12 for WHMCS 4 ####
_(Release Date: Jul 25, 2012)_

  * Extended attributes for me.uk domains

#### Version 1.2.4 for WHMCS 5 ####
_(Release Date: Jul 25, 2012)_

  * Extended attributes for me.uk domains

#### Version 1.1.11 for WHMCS 4 ####
_(Release Date: Jun 19, 2012)_

  * Fixed domain name case sensitivity in the sync script

#### Version 1.2.3 for WHMCS 5 ####
_(Release Date: Jun 19, 2012)_

Fixed domain name case sensitivity in the sync script

#### Version 1.1.10 for WHMCS 4 ####
_(Release Date: May 3, 2012)_

  * Fixed issue with incorrect parameters on domain contact details saving.
  * Replaced classes NamecheapApi and NamecheapApiException with NamecheapRegistrarApi and NamecheapRegistrarApiException to avoid conflict with Namecheap SSL module.
  * Added default params for .de domains to request(DEConfirmAddress=DE,DEAgreeDelete=Yes)
  * Added Base64 encoding for EPPCode.
  * Fixed bug with parsing domain transfer data that prevent domains from being recognized as already transferred.

#### Version 1.2.2 for WHMCS 5 ####
_(Release Date: May 3, 2012)_
  * Fixed issue with incorrect parameters on domain contact details saving.
  * Replace classes NamecheapApi and NamecheapApiException with NamecheapRegistrarApi and NamecheapRegistrarApiException to avoid conflict with Namecheap SSL module
  * Added default params for .de domains to request(DEConfirmAddress=DE,DEAgreeDelete=Yes)
  * Added Base64 encoding for EPPCode.
  * Fixed bug with parsing domain transfer data that prevent domains from being recognized as already transferred.
  * Removed custom client warnings regarding Whoisguard.
  * Dropped .asia domain entries in favor of the standard WHMCS.NOTE: Unfortunately, you still need to add this code right after other $additionaldomainfields[".asia"][.md](.md) entries in the file includes/additionaldomainfields.php
```
$additionaldomainfields[".asia"][] = array(
"Name" => "Locality",
"Type" => "dropdown",
"Options" => "af,bd,ck,in,jp,kg,mh,nz,ps,sg,th,tv,aq,bt,cy,id,kz,la,fm,nu,pg,sb,tl,ae,am,bn,fj,ir,ki,lb,mn,nf,ph,lk,tk,uz,au,kh,ge,iq,kp,mo,mm,om,qa,sy,to,vu,az,cn,hm,il,kr,my,nr,pk,ws,tw,tr,vn,bh,cc,hk,jo,kw,mv,np,pw,sa,tj,tm,ye"
);
```

#### Version 1.1.8 ####
_(Release Date: Sep 29, 2011)_

  * Fixed showing of Whoisguard related error messages in the Client Area
  * Improved Sync script to produce more detailed report on dates synchronisation

#### Version 1.1.7 ####
_(Release Date: Mar 31, 2011)_

  * Removed Free PositiveSSL promotional offer.

#### Version 1.1.6 ####
_(Release Date: Feb 16, 2011)_

  * Feature to synchronize expirydate and nextduedate for all active domains. This feature is useful for expiry date synchronization after domain renewal and reactivation.

#### Version 1.1.5 ####
_(Release Date: Feb 08, 2011)_

  * Functionality to reactivate expired domains added to the renew function

#### Version 1.1.4.1 ####
_(Release Date: Jan 28, 2011)_

  * Nextduedate is set the same as expirydate

#### Version 1.1.4 ####
_(Release Date: Dec 08, 2010)_

**New/Enhancement**

  * .ASIA domains are now supported
  * Synchronization script namecheapsync.php added that synchronizes domain transfer status, expiration and next due dates for  domains that are transferred (check registrar module configuration page for setup notes)

#### Version 1.1.3 ####
_(Release Date: Oct 22, 2010)_

**New/Enhancement**
  * Added support for new required fields for .ca domains (**_NOTE:_** WHMCS 4.3.1a or higher required)
  * Allow specifying FreePositiveSSL auto adding on domain creation

#### Version 1.1.2 ####
_(Release Date: Sept 21, 2010)_

**New/Enhancement**

  * The algorithm used for phone country code checking was rewritten.
  * Support for .eu registerations.

**_NOTE:_** At this time WHMCS doesn't support extended attributes for .eu domains. You have to add the following code at the end of the file includes/additionaldomainfields.php before ? >
```
$additionaldomainfields[".eu"][] = array(
"Name" => "Language for Address Used",
"Type" => "dropdown",
"Options" => "Bulgaria,Czech,Danish,Dutch,English,Estonian,Finnish,French,German,Greek,Hungarian,Italian,Latvian,Lithuanian,Maltese,
Polish,Portuguese,Romania,Slovak,Slovenian,Spanish,Swedish"
)
```

#### Version 1.1.1 ####
_(Release Date: Sept 11, 2010)_

**Bugs Fixed**

  * Issue with billing/admin/tech contacts not being set properly when using custom contact details.
  * Fixed warning php message (Warning: Wrong parameter count for preg\_replace() in /home/trainer/public\_html/portal/modules/registrars/namecheap/namecheapapi.php on line 111)
  * Changes made in regards to warning node for sethosts (domains using custom DNS) and warning node for create domains using unregistered nameservers

#### Version 1.1.0 ####
_(Release Date: Jul 12, 2010)_

**New/Enhancement**

  * New Namecheap API wrapper
  * Allowed option to specify coupon code
  * Allowed separate entries for sanbox user/api key
  * Registration and extended attributes for .us, .ca, .co.uk and .org.uk

#### Version 1.0.2 ####
_(Release Date: Feb 14, 2010)_

**Bugs Fixed**

  * Client IP was not passing properly
  * Removed error during registration

**New/Enhancement**

  * Code reformatted
  * Phone number reformatted to allow country codes to be recognized properly