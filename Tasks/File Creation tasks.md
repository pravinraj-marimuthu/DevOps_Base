Task Description:

1. Create a directory called ""my_folder"", navigate into it, and create a file named ""my_file.txt"" with some text. Then, create another file named ""another_file.txt"" with some text. Concatenate the content of ""another_file.txt"" to ""my_file.txt"" and display the updated content. Finally, list all files and directories in the current directory.
   
   + _**my_folder**_ creation

      ```
       mkdir my_folder | ls
      ```

      ![image](https://github.com/user-attachments/assets/39267f66-fdaa-496d-a5d4-3722b2d7cf30)

    + _**my_file.txt**_ and _**another_file.txt**_ creation with some text

      ```
       echo "Hello" > my_file.txt | echo "This is Pravinraj" > another_file.txt
      ```

      ![image](https://github.com/user-attachments/assets/df074e50-af80-4fdb-802b-b999a3ce47c1)

    + Concatenate the content of _**another_file.txt**_ to _**my_file.txt**_

      ```
       cat another_file.txt >> my_file.txt
      ```

       ![image](https://github.com/user-attachments/assets/6c9b870b-3183-4c32-b39f-7970770ab310)

    + Display **_my_folder_** directory

       ![image](https://github.com/user-attachments/assets/a445150c-f50a-4b04-a057-7dd40978a4a7)
