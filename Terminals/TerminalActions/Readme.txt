Prerequisites:

1. One must copy the following folder \\fileserver\Public\QA\DragosSuma\sim390dm onto the C:\ of the machine where the test will run

2. One must install the following terminal before running the flow: \\fileserver\Public\GTatu\terminals\BlueZoneDesktop 6.1 PS: the license for BlueZone is found here : \\fileserver\Public\GTatu\terminals and it's named seagull.saf

Test description:

The aim of the test is to start sim390 mainframe simulator , connect to it using BlueZone terminal , edit a file and check using Internet Explorer that the changes were saved. 

The sim390 mainframe emulator has a HTTPD server build in , along with some other nice features such as email, ftp , but for this simple test we will use the HTTPD server. 

Some resourcer regarging the MUSIC/OS ( the operating system which is installed on sim390) can be found here :

https://uipath.atlassian.net/wiki/spaces/FAN/pages/336986192/01+-+Mainframe+Emulation
http://webpages.mcgill.ca/staff/group3/dedwar1/web/msi/musicsp.html
http://www.canpub.com/teammpg/de/sim390/musdemo.txt

