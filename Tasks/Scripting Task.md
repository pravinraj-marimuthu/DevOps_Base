## Task Description

1. Create a shell script to print the HTTP error code of guvi.in & print the success/failure message based on the error code response

   - Script to print the response code and message

     ```
     #!/bin/bash
     
     #get the URL from user
     
     read -p "Enter the URL: "  url
     
     #curling the input and filtering the error code and error messages
     
     code=$(curl -s -I $url | head -1 | awk {'print $2'})
     message=$(curl -s -I $url | head -1 | awk {'print $3,$4'})
     
     #printing the value seperately
     
     echo "Error code - $code"
     echo "Error message - $message"
     ```
     
     ![image](https://github.com/user-attachments/assets/04c60807-2e93-4f2f-84d8-6ce2233b915a)

     <br />

2. Given a file, replace all occurrence of the word "give" with "learning" from 5th line till the end in only those lines that contain the word "welcome"

   - Script to replace "Give" with "Learning" only in the lines that contains "Welcome"
  
     ```
     #!/bin/bash

     num_lines=$(wc -l < /home/pravinrajmarimuthu/textfile.txt | awk '{print $1}')

     for ((i=1; i<=num_lines; i++)); do
              if [ $i -ge 5 ]; then
                     if grep -q "Welcome" <(sed -n "${i}p" /home/pravinrajmarimuthu/textfile.txt); then
                        sed -i "${i}s/Give/Learning/" /home/pravinrajmarimuthu/textfile.txt
                     fi
              fi
     done
     ```
   - Pre and Post execution of the above script 

     ![image](https://github.com/user-attachments/assets/0b0b4fcf-7791-46fa-a02a-122bd8a5d961)

     

   
