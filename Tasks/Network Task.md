## Task Description

1. Get me the IP address of a particular domain (guvi.in). How do I find my CPU/memory usage of my server?. Test the connectivity between 2 nodes?

   - IP address of guvi.in

     ```
     nslookup guvi.in
     ```
     ![image](https://github.com/user-attachments/assets/9560259e-b9f7-4c2d-b12b-f347334265ad)

   - CPU/Memory usage of server

     ```
     top
     ```
     ![image](https://github.com/user-attachments/assets/ccaeb65d-b640-47ae-99b9-05041e8c8e15)
     ```
     free -h
     ```
     ![image](https://github.com/user-attachments/assets/8fb1d33d-8512-4be7-aaa5-19e80fed37ef)

   - Test the connectivity between 2 servers
  
     ```
     sudo ping -c3 104.26.4.88
     ```
     ![image](https://github.com/user-attachments/assets/a21c4305-74e0-4493-be87-be595b6723b1)

2. I have deployed an application in guvi.com:9000, and logs show my app is running, but I’m unable to view the page. Check whether my port is open or not ?

   - Check whether port is open or not
  
     ```
     telnet guvi.com 9000 
     ```
       If port is open, the request will be connected. If not, it will end up with an error
     
     ![image](https://github.com/user-attachments/assets/4ddb2043-7b9d-4f13-b3d5-4325bc02d522)
     ![image](https://github.com/user-attachments/assets/0682601e-369f-4aea-9c3d-d60adbb3a86e)

