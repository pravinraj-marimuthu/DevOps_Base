## Task Description

1.  Launch an EC2 instance (Linux and Windows) along with a web server. Then, create an EBS volume of 5 GB, attach it to an EC2 machine (Linux and Windows), and take a snapshot. Finally, create an EBS volume using the taken snapshot

    - Launch an EC2 instance along with a web server
  
      ![image](https://github.com/user-attachments/assets/3477242e-57fe-49d6-a458-744880f83e10)
      
      ![image](https://github.com/user-attachments/assets/9f2122eb-db51-4828-a2bc-a2c33c291fc6)

    - create an EBS volume of 5 GB and attach it to an EC2 machine and take a snapshot
  
      ![image](https://github.com/user-attachments/assets/b665df7a-b021-43a0-afad-15a3019018d0)

      ![image](https://github.com/user-attachments/assets/417592e7-b219-4383-981e-34fe4fe197a6)
      
      ```
      mkdir /mnt/ebs_new_volume
      sudo mount /dev/nvme1n1 /mnt/ebs_new_volume
      lsblk
      ls -l /mnt/ebs_new_volume
      ```
      
      ![image](https://github.com/user-attachments/assets/bf9be844-e0ae-4116-9b24-86eee22e64d2)

      ![image](https://github.com/user-attachments/assets/ac9fb98b-2a2d-41d7-b632-f6655d7179f1)

      ![image](https://github.com/user-attachments/assets/49892ca3-828b-42f5-ac39-5d7bd4667978)


    - Finally, create an EBS volume using the taken snapshot.
      
      ![image](https://github.com/user-attachments/assets/98ad9a11-1b9d-49dc-817e-3b854042a4cf)
  
      ![image](https://github.com/user-attachments/assets/590e960f-31c3-4398-b6e0-e2799bba3c01)

      ![image](https://github.com/user-attachments/assets/db377599-a29e-44b8-9dae-253680240320)

      ![image](https://github.com/user-attachments/assets/5e26bedb-466f-495e-b618-7a8f999227be)
  
      Volume taken from snapshot holds the data from volume we created in the beginning. 

      ![image](https://github.com/user-attachments/assets/9e0140bf-39f1-46fe-8826-5ffe575d3fb2)

      ___

