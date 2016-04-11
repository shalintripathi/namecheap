[![](http://files.namecheap.com/graphics/nslogo.gif)](http://www.Namecheap.com)

We have two WHMCS plugins available.
  1. **Namecheap.com WHMCS Registrar Plugin** (see below)<br><i>If you want to register domain through Namecheap.com for your customers</i>
<ol><li><b><a href='NamcheapWHMCSSSLModule.md'>Namecheap.com WHMCS SSL Module</a></b><br><i>If you want to sell SSL certificates to your customers using WHMCS</i></li></ol>

<h2>Namecheap.com WHMCS Registrar Plugin</h2>
<hr />

<font size='3px'><b>Note:</b></font> <font size='2.5px'><i>We have two variants of Namecheap.com WHMCS Registrar plugins for WHMCS version 4 and 5. You need to download and install Namecheap.com WHMCS Registrar Plugin version 1.1.12 is for WHMCS version 4 and Namecheap.com WHMCS Registrar Plugin version 1.2.7 for WHMCS 5.</i></font>

<hr />

<h3>Updated on Oct 22, 2013 to Version 1.2.7 for WHMCS 5</h3>

<ul><li>Added .fr, .sg, .com.sg, .fr, .net.au, .org.au, .com.au, .es, .com.es, .nom.es, .org.es support<br>
</li><li>Removed error "Domain name not found" for domains in any status, except for not in "Active" or "Expired"<br>
</li><li>Added "Job Title" additional field for .ca and .au domains<br>
</li><li>All errors from API response are returned by the module (in case there is more than one error)<br>
</li><li>Fixed error with domains that have been added in punycode to WHMCS<br>
</li><li>Added conversion for registrant state/province and zip code fields for .ca domains according to the registry requirements</li></ul>

<h3>Updated on Jul 25, 2012 to Version 1.1.12 for WHMCS 4</h3>
<ul><li>Extended attributes for .me.uk domains</li></ul>

<a href='http://code.google.com/p/namecheap/wiki/ReleaseNotesforWHMCSRegistrarPlugin'>ReleaseNotes</a>

Namecheap.com WHMCS Registrar plug-in is an open-source plug-in that is distributed free of charge. It focuses on integrating Namecheap as a domain registrar at WHMCS.<br>
<br>
After the integration you can setup Namecheap as the default registrar for your customers and decide which services and TLDs to offer to your customers from within the WHMCS admin area.<br>
<br>
<h3>Pre-requisites</h3>
<ul><li>Access to WHMCS admin area.<br>
</li><li>An understanding of <a href='http://www.namecheap.com/support/api/api.aspx'>Namecheap’s environments</a>.<br>
</li><li>Namecheap account with API access enabled on the desired environment.</li></ul>

NOTE: Namecheap has a production as well as a test server environment. The test server environment is called Sandbox. We urge you to test the WHMCS Registrar plug-in in our <a href='http://www.sandbox.namecheap.com'>sandbox environment</a>, before pointing it to production. For more detailed information, please visit the developer's site at <a href='http://www.namecheap.com/support/api/api.aspx'>http://www.namecheap.com/support/api/api.aspx</a>

<h3>Download and Installation</h3>

<ol><li><a href='http://code.google.com/p/namecheap/downloads/list'>Download</a> the latest plugin (namecheap-whmcs.x.x.zip) archive and extract it.<br>
</li><li>Create a folder called <b>namecheap</b> under Modules/Registrar in your WHMCS root directory and paste the downloaded <b>namecheap.php</b> and <b>namecheapapi.php</b> files inside the folder (the namecheap.php and namecheapapi.php files are located inside the downloaded archive). The plug-in installation is complete.</li></ol>


<h3>Configuration</h3>

To configure WHMCS for use with Namecheap, perform the following steps:<br>
<br>
<br>
<ol><li>Login to your <b>WHMCS admin</b> panel.<br>
</li><li>Click on <b>Setup</b> menu, select <b>Products/Services</b> and click on <b>Domain Registrars</b>.<br>
</li><li>Click on Activate next to Namecheap in the list:</li></ol>

<blockquote><img src='http://files.namecheap.com/images/googlecode/Activate_Namecheap.png' /></blockquote>

<blockquote>4. Enter your API credentials. If you wish to try out the plug-in in sandbox, make sure to enter your sandbox username, sandbox API key in the corresponding text boxes and check the “Test Mode” checkbox:</blockquote>

<blockquote><img src='http://files.namecheap.com/images/googlecode/Configure_Namecheap.png' /></blockquote>

<blockquote>5. <b>Optional settings:</b>
</blockquote><ul><li>If you have a <b>promotional coupon code</b> from Namecheap you may enter it in the module settings. The discounted price will be automatically applied on your orders according to the coupon pricing.</li></ul>

<ul><li><b>SyncNextDueDate</b> option will enable expiry date sync script that will update the expiry and next due dates on the domain names. To utilize this feature you will need to setup a cron with the command below to run every few days:</li></ul>

<blockquote><pre><code> php -q /home/houhut/public_html/whmcs/modules/registrars/namecheap/namecheapsync.php </code></pre></blockquote>

<ul><li>If you’re having any issues with the module it is recommended to enable <b>DebugMode</b> and check the logs under Utilities > Logs > Module Log. If this option is disabled the module will be logging only errors returned by the module.<br>
</li></ul><blockquote>6.  Click <b>Save Changes</b>.</blockquote>

That’s it. The Namecheap plug-in is now ready for use and will function just like any other built-in WHMCS registrar module. You can now make Namecheap as the automatic registrar, configure TLDs and services for all your customers. To perform these actions, click on the <b>Setup</b> menu, select <b>Products/Services</b> and click on <b>Domain Pricing</b> in your WHMCS admin panel:<br>
<br>
<img src='http://files.namecheap.com/images/googlecode/domain_pricing.png' />

You can refer to <a href='http://docs.whmcs.com/Domains_Configuration'>http://docs.whmcs.com/Domains_Configuration</a> for more information.<br>
<br>
To add additional fields required for our module (language for IDN domains, Job Title field for .CA and .AU domains, extended attributed for .FR domains) you will need to connect our own additionaldomainfields.php file. To do this, please add the following strings in the end of includes/additionaldomainfields.php file:<br>
<br>
If<br>
(file_exists(dirname(FILE)."/../modules/registrars/namecheap/additionaldomainfields.php"))<br>
{<br>
<blockquote>include<br>
dirname(FILE)."/../modules/registrars/namecheap/additionaldomainfields.php";<br>
}</blockquote>

<h2>Support</h2>
Please use the <a href='http://code.google.com/p/namecheap/issues/list'>Issues</a> page to report bugs and provide feedback.Alternatively, you can also <a href='http://support.Namecheap.com'>submit a ticket</a> for assistance.