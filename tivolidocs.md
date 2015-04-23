## Linux Installation

This document assumes you've registered your server for data backup services with Division of IT. You will received an email with relevant information for your backup node from the Division of IT. Refer to that while going through this.

Download the client from IBM by looking at this [link](http://www-01.ibm.com/support/docview.wss?uid=swg21052223) before installing. For the rest of this document we are assuming a 64bit Operating System. Adjust accordingly.

1. Download the client from IBM

   `wget ftp://public.dhe.ibm.com/storage/tivoli-storage-management/maintenance/client/v7r1/Linux/LinuxX86/BA/v711/7.1.1.0-TIV-TSMBAC-LinuxX86.tar`

2. As root find the downloaded file in step 1 and unpackage the file.

   `tar -xvf 7.1.1.0-TIV-TSMBAC-LinuxX86.tar`

3. Install the GSKit Package

   `rpm -U gskcrypt64-8.0.14.43.linux.x86_64.rpm gskssl64-8.0.14.43.linux.x86_64.rpm`

4. Install the TSM API and dependencies

   `yum localinstall TIVsm-API64.x86_64.rpm`
   `yum localinstall TIVsm-APIcit.x86_64.rpm`

5. Install the Backup-Archive Client

   `yum localinstall TIVsm-BA.x86_64.rpm`
   `yum localinstall TIVsm-BAcit.x86_64.rpm`
   `yum localinstall TIVsm-BAhdw.x86_64.rpm`

6. Refer to email from DivIT confirmation email contents and edit accordingly

7. Start the Command Line Client and use the node_name as user_id and password in the confirmation email

8. Add the TSM Client Acceptor Daemon Service to services

    `chkconfig --add dsmcad`
    `chkconfig dsmcad on`
    `service dsmcad start`
