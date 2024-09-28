## Task Description:

1. Launch Linux EC2 instances in two regions using a single Terraform file.

   **main.tf**

      ```
      # Define the provider for the first region
      
      provider "aws" {
        alias  = "us_east"
        region = "us-east-1"
      }
      
      # Define the provider for the second region
      
      provider "aws" {
        alias  = "us_west"
        region = "us-west-2"
      }
      
      # Create an instance in the first region
      
      resource "aws_instance" "TerraformInstance_01" {
        provider = aws.us_east
        ami           = "ami-0ebfd941bbafe70c6"
        instance_type = "t2.micro"
      }
      
      # Create an instance in the second region
      
      resource "aws_instance" "TerraformInstance_02" {
        provider = aws.us_west
        ami           = "ami-08d8ac128e0a1b91c"
        instance_type = "t2.micro"
      }
      
      # Output the public IP of the instance in the first region
      
      output "us_east_instance_ip" {
        value = "The IP of first Instance is ${aws_instance.TerraformInstance_01.public_ip}"
      }
      
      # Output the public IP of the instance in the second region
      
      output "us_west_instance_ip" {
        value = "The IP of second Instance is ${aws_instance.TerraformInstance_02.public_ip}"
      }
      ```
   **terraform init**

      ![image](https://github.com/user-attachments/assets/1a5d2c6e-60bb-49f7-887f-6ec81ac4d297)

   **terraform plan**

      ![image](https://github.com/user-attachments/assets/adc6f407-4692-453b-b503-5a9aa1e80c73)
      ![image](https://github.com/user-attachments/assets/52d6766c-f71a-4a40-8948-4f0202826179)
   
   **terraform apply**

      ![image](https://github.com/user-attachments/assets/e61c508c-6448-40a0-b8e8-d6df6c7e0097)
      ![image](https://github.com/user-attachments/assets/c2b5f0e1-1c78-4109-8010-ecbc66411ab1)
      ![image](https://github.com/user-attachments/assets/fa6fea7f-f2fc-4d03-95f1-3a8b0c292748)

   **terraform output**

      ![image](https://github.com/user-attachments/assets/a4706d0a-0950-4907-a055-44d3038ef7e2)

   ## First Instance on us-east-1

      ![image](https://github.com/user-attachments/assets/59af7524-a0b6-4ad6-8fb0-bbc324f80b21)

   ## Second Instance on us-west-2

      ![image](https://github.com/user-attachments/assets/616d3ad8-9b17-487e-b6fa-f39eae98c322)
   ___
