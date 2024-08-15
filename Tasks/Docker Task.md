## Task Description:


1. Install docker on EC2 and explore the docker commands (docker images, containers, volumes, network)
   
   - Install docker on EC2
     ```
     sudo yum install -y Docker
     docker -v
     ```
     ![image](https://github.com/user-attachments/assets/cb5a5c35-4bde-432b-b593-6e2329f932e8)

   - Docker Setup
     ```
     sudo service docker start
     sudo usermod -a -G docker ec2-use
     ```
     ![image](https://github.com/user-attachments/assets/c2920383-d49b-4475-8642-9562e610507e)
   
   - Docker Commands
     ```
     docker search hello-world
     ```
     ![image](https://github.com/user-attachments/assets/0774755f-660a-47f9-b5fb-97e003028c17)

     ```
     docker pull hello-world
     ```
     ![image](https://github.com/user-attachments/assets/bdb2a86a-7885-4388-8630-6046d7a0111f)
     ```
     docker images
     ```
     ![image](https://github.com/user-attachments/assets/6a9b4eca-3047-4e66-bd90-ed7f19cb30a3)
  
     ```
     docker run hello-world
     ```
     ![image](https://github.com/user-attachments/assets/f9bfbabb-7278-4277-aee8-fe9e3cff2cba)
     ```
     docker run --name my_container -d alpine sh -c "while true; do sleep 3600; done"
     docker ps
     ```
     ![image](https://github.com/user-attachments/assets/9e60005a-b5a3-4fd5-9019-ad80318080d7)
     ```
     docker volume create my_docker_volume
     docker volume ls
     docker volume inspect my_docker_volume
     docker volume rm my_docker_volume
     ```
     ![image](https://github.com/user-attachments/assets/8e8b5caa-fbf3-461b-8c5f-5c1e8b9473f6)
     ![image](https://github.com/user-attachments/assets/f0ae18f0-d560-4804-9240-443ba77de7aa)
     ```
     docker network create mydocnet
     docker network ls
     docker network inspect mydocnet
     docker network rm mydocnet
     docker network ls
     ```
     ![image](https://github.com/user-attachments/assets/77874a4a-eaaf-40e1-8319-fe76767c9766)
     ![image](https://github.com/user-attachments/assets/c561c767-5706-484f-ab37-129803e54836)
     ![image](https://github.com/user-attachments/assets/0dddb54a-4d7b-4f5c-8bfb-37b70da0053d)

