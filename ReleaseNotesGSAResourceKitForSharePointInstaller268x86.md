# Release Notes for the GSA Resource Kit for SharePoint Installer v2.6.8 32-bit #

Release Notes


Google Search Appliance Resource Kit for SharePoint 2.6.8 (32-bit)

This document contains the release notes for Google Search Appliance Resource Kit for SharePoint 2.6.8 (32-bit).
The following sections describe the release in detail and provide information that supplements the main documentation.
See the Issues Tab on the Code Site for the current list of known issues and workarounds.

Web Site: http://code.google.com/p/google-enterprise-connector-sharepoint/issues/list


Release 2.6.8, 08 Mar, 2011


INTRODUCTION

---

This is an early access release for wide evaluation and usage. Your feedback is important to us. Keep in mind that we are continuing to work on Google Search Appliance Resource Kit for SharePoint 2.6.8 (32-bit) and things may change in the future.

Pre-requisites

---

**SharePoint 2007 (WSS 3.0, MOSS 2007) or SharePoint 2010 server.** Windows Server 2003 Enterprise server/Windows Server 2008 Enterprise server.
**Microsoft .Net Framework 2.0.** IIS 6.0/IIS 7.0.

Note:

---

If you have already installed Google Services for SharePoint or Google Search Box for SharePoint earlier using the old installer (i.e. GSS.msi or GSBI.msi or Google Search Appliance Resource Kit for SharePoint 1.x.x), please uninstall them before trying the Google Search Appliance Resource Kit for SharePoint 2.6.8 installer.

Features

---

1. Google Search Appliance Resource Kit for SharePoint 2.6.8 (32-bit) installer bundles following components:
> a) Google Search Box for SharePoint: It represents Google Search Box for SharePoint. When selected, the Google Search Box for SharePoint is enabled on all SharePoint web applications on a machine, which share the same search control.
> b) Google Services for SharePoint: The Google Services for SharePoint are custom web services used by the Google Search Appliance Connector for Microsoft SharePoint 2007 and Microsoft SharePoint 2010.
> c) GSA Resource Kit for SharePoint: It represents the following utilities:
> > -Google Search Box for SharePoint Test Utility : It is used to verify the Google Search Box for SharePoint parameters, cookies and headers.
> > -GSA Security SPI Simulator: It is used to test Google SAML Bridge for Windows without involving the complexity of the search appliance. Once you know that the SAML Bridge works, you can reconfigure it to work with the search appliance.
> > -Google SAML Bridge for Windows: It enables Google Search Box for SharePoint to perform search on NTLM contents.

Issues fixed from last release:

---

1) [Issue 105](https://code.google.com/p/googlesearchapplianceconnectors/issues/detail?id=105) - Support site/list level search scope (context sensitive) with Google Search Box in SharePoint


> o Earlier version of Google Search Box for SharePoint supported search at a global level. There was no mechanism to restrict the search results to a particular site/ list/ folder in SharePoint.
> o Hence, added support for context-sensitive search with Google Search Box for SharePoint 2007 and SharePoint 2010
> o Scopes make it possible to narrow searches to particular locations/entities. Added a scopes dropdown alongwith Google Search Box for SharePoint. Scopes dropdown consists of the following scopes : Current Site, Current Site and all subsites, Current List, Current Folder and Current Folder and all subfolders.
> o Used the technique of "directory restricted search" for getting the search results restricted to a particular scope selected by the user. Hence, added code to get the currently selected scope's URL.
> o Modified the search request sent to the GSA to include the scope search parameter. Used the 'sitesearch' parameter which will hold the currently selected scope's URL value.
> o With this, the search results are restricted to the scope selected by the user.
> o Also added code which will persist the values of public search checkbox status, search query term and selected scope while navigating between search results using previous and next buttons.

Version Compatibility

---

The Google Services for SharePoint are supported on the following SharePoint versions:
**Microsoft Office SharePoint Server 2007 (MOSS 2007)** Microsoft Windows SharePoint Services 3.0 (WSS 3.0)


Platform Support

---

Google Resource Kit for SharePoint 2.6.8 (32-bit) can be installed on Windows Server 2003 Enterprise (32-bit)/Windows Server 2008 Enterprise (32-bit) Operating System.

Note:

---

> a) There are separate installers for 32-bit and 64-bit Operating System.
> b) The 64-bit installer is supported on machines with x64 platform.

Certified Against

---

Microsoft Windows Server 2008
Enterprise Edition
Intel  Xeon  CPU
E5504 @ 2.00GHz, 4.00 GB of RAM

Microsoft Windows Server 2003
Enterprise Edition
Intel  Xeon  CPU
E5504 @ 2.00GHz, 2.00 GB of RAM

Known Issues/Limitations

---

1. The Installer does not validate the port number for 'GSA Resource Kit for SharePoint'. User needs to enter a valid non-conflicting port during installation. Assigned port number could be changed even after Installation directly through IIS Manager.
2. The Installer does not validate the 'Artifact Consumer' URL on "Google SAML Bridge for Windows - Configuration Wizard".
3. Cancelling Installer does not intiate rollback of the installed components. You need to run installer again in 'remove' mode to clean up the installed components.
4. If the 32 bit installer is executed on 64 bit machine, then the installer does not give any error message.
5. If a new web application is added after the installation of search box,this web application does not show search box.