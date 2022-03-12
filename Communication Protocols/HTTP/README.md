# HTTP

HTTP protocal is stateless but under the hood it uses TCP that is statefull 

OSI Layer 7 Protocol

![image](https://user-images.githubusercontent.com/7610065/158011569-a94f31ca-f3b6-4158-abf0-e7a43ec83fe1.png)

![image](https://user-images.githubusercontent.com/7610065/158011597-29a46d25-1de9-497d-a3c3-aadce6d9a6fa.png)

To open a connection we have to do 3-way handshake

HTTP 1.0 (1996-1997)

open-close connection for each request

![image](https://user-images.githubusercontent.com/7610065/158011981-8a605e80-7da8-41c1-acad-3d9485335245.png)
![image](https://user-images.githubusercontent.com/7610065/158011956-fb851532-df1b-496a-86d9-a32db4491c15.png)

HTTP 1.1 (1997-2015)

connection is only closed if server serves all the client requests, this also brings concepts of e-tags and caching
Keep alive header also send with the request

![image](https://user-images.githubusercontent.com/7610065/158012097-18d6953c-196b-4277-8833-3afb7a89f4c3.png)
![image](https://user-images.githubusercontent.com/7610065/158012082-e5c46d90-db2c-49d1-ba38-200c172857a1.png)

HTTP 2.0 (2015-Now)

![image](https://user-images.githubusercontent.com/7610065/158012237-288a081c-5b01-489e-ae94-d303339b34e3.png)

HTTP 3.0

Still experimental

![image](https://user-images.githubusercontent.com/7610065/158012424-b0ccf7d6-de1a-449f-b732-2d8b4b328582.png)

