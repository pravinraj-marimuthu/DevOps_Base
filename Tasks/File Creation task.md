## Task Description:


1. Create a directory called ""my_folder"", navigate into it, and create a file named ""my_file.txt"" with some text. Then, create another file named ""another_file.txt"" with some text. Concatenate the content of ""another_file.txt"" to ""my_file.txt"" and display the updated content. Finally, list all files and directories in the current directory.
   
   - Create directory named _**my_folder**_ 

      ```
       mkdir my_folder | ls
      ```

      ![image](https://github.com/user-attachments/assets/39267f66-fdaa-496d-a5d4-3722b2d7cf30)

    - _**my_file.txt**_ and _**another_file.txt**_ creation with some text

      ```
       echo "Hello" > my_file.txt | echo "This is Pravinraj" > another_file.txt
      ```

      ![image](https://github.com/user-attachments/assets/df074e50-af80-4fdb-802b-b999a3ce47c1)

    - Concatenate the content of _**another_file.txt**_ to _**my_file.txt**_

      ```
       cat another_file.txt >> my_file.txt
      ```

       ![image](https://github.com/user-attachments/assets/6c9b870b-3183-4c32-b39f-7970770ab310)

    - Display **_my_folder_** directory
  
      ```
       ls -l
      ```

       ![image](https://github.com/user-attachments/assets/a445150c-f50a-4b04-a057-7dd40978a4a7)

___

2. Create 20 files with .txt extensions and rename the first 5 files to .yml extension and Print the latest created top 5 files among the total no of files".

   - Create 20 files with .txt extension
  
      ```
       touch file_{1..20}.txt
      ```

       ![image](https://github.com/user-attachments/assets/959db305-77fe-45d7-b759-bf69b2af1556)

      ```
       for i in {1..5}; do mv "file$i.txt" "file$i.yml"; done
      ```

      ![image](https://github.com/user-attachments/assets/a1095dc0-02b7-46b5-9d73-25945bd1db11)

       ```
       ls -lv | head -6
      ```

       ![image](https://github.com/user-attachments/assets/3c7eb18d-6b23-4b03-b4c7-6bbb98a8b3fc)


___
