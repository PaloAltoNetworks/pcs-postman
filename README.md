# pcpostman

# Used for Postman collections and environments relating to Prisma Cloud API requests

To use these collections and environment, there are a few setup pieces after importing the 3 files into Postman:
1. [Import the 3 files](https://learning.postman.com/docs/getting-started/importing-and-exporting-data/) in this repo (2 Collections and 1 Environment) into Postman.

1. Set the Prisma Cloud API and Console URL in the [Postman Environment variable](https://learning.postman.com/docs/sending-requests/variables/)

Prisma Cloud Admin Console | 	Prisma Cloud API Endpoint
------------ | -------------
https://app.prismacloud.io	| https://api.prismacloud.io
https://app2.prismacloud.io	| https://api2.prismacloud.io
https://app3.prismacloud.io	| https://api3.prismacloud.io
https://app4.prismacloud.io	| https://api4.prismacloud.io
https://app.anz.prismacloud.io	| https://api.anz.prismacloud.io
https://app.eu.prismacloud.io	| https://api.eu.prismacloud.io
https://app2.eu.prismacloud.io	| https://api2.eu.prismacloud.io
https://app.gov.prismacloud.io	| https://api.gov.prismacloud.io
https://app.prismacloud.cn	| https://api.prismacloud.cn
https://app.ca.prismacloud.io	| https://api.ca.prismacloud.io
https://app.sg.prismacloud.io	| https://api.sg.prismacloud.io

1. To get the address/URL for your Console, go to *Compute > Manage > System > Downloads*, and copy the string under **Path to Console**
**The URL should look something like this:** https://us-east1.cloud.twistlock.com/us-1-123456789


-Set your access/secret key in the BODY of the /login request (Does this make sense? Should it be an env variable?)
