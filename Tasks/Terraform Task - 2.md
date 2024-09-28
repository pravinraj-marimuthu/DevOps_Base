## Task Description:

1. Create 2 EC2 instances on 2 different regions and install nginx using terraform script.

   main.tf

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
        user_data     = <<-EOF
                        #!/bin/bash
                        sudo yum update -y
                        sudo yum install nginx -y
                        sudo systemctl start nginx
                        sudo systemctl enable nginx
                        EOF
      }
      
      # Create an instance in the second region
      
      resource "aws_instance" "TerraformInstance_02" {
        provider = aws.us_west
        ami           = "ami-08d8ac128e0a1b91c"
        instance_type = "t2.micro"
        user_data     = <<-EOF
                        #!/bin/bash
                        sudo yum update -y
                        sudo yum install nginx -y
                        sudo systemctl start nginx
                        sudo systemctl enable nginx
                        EOF
      }

      resource "aws_security_group" "sg_2e8qwfnqf90" {
      name        = "example_sg"
      description = "Allow SSH and HTTP"
      vpc_id      = "vpc_348y23059wfnwefp"
    
      ingress {
        description = "SSH"
        from_port   = 22
        to_port     = 22
        protocol    = "tcp"
        cidr_blocks = ["0.0.0.0/0"]
      }
    
      ingress {
        description = "HTTP"
        from_port   = 80
        to_port     = 80
        protocol    = "tcp"
        cidr_blocks = ["0.0.0.0/0"]
      }
    
      egress {
        from_port   = 0
        to_port     = 0
        protocol    = "-1"
        cidr_blocks = ["0.0.0.0/0"]
      }
    
      tags = {
        Name = "sg_2e8qwfnqf90"
      }
    }
      
      # Output the public IP of the instance in the first region
      
      output "us_east_instance_ip" {
        value = "The IP of first Instance is ${aws_instance.TerraformInstance_01.public_ip}. Configure your web server here - /etc/nginx/nginx.conf"
      }
      
      # Output the public IP of the instance in the second region
      
      output "us_west_instance_ip" {
        value = "The IP of second Instance is ${aws_instance.TerraformInstance_02.public_ip}. Configure your web server here - /etc/nginx/nginx.conf"
      }
      ```

   ```terraform plan```

      ![image](https://github.com/user-attachments/assets/37516b35-21a8-4da8-b524-e232785367c0)

   ```terraform apply```

      ![image](https://github.com/user-attachments/assets/7c865157-0d66-4cab-b7a4-e36a1847406a)
      ![image](https://github.com/user-attachments/assets/031fbaf5-6a6f-49be-a812-8088fda299f0)
      ![image](https://github.com/user-attachments/assets/93430741-c9f9-4ecd-aafc-3fb0ea2ec22b)
      ![image](https://github.com/user-attachments/assets/53e82cc2-1618-4453-93d7-21381daed4fd)

    First Instance on us-east-1 and NGINX installed
 
      ![image](https://github.com/user-attachments/assets/83ad4c0d-44d8-4427-b960-e74f3fdbab6d)
      ![image](https://github.com/user-attachments/assets/c8a8edb8-f95b-4af6-8d98-761976967bef)
      ![image](https://github.com/user-attachments/assets/abdfa7a5-4691-4a02-99b9-2e4a0f9e9f15)

    First Instance on us-east-1 and NGINX installed

      ![image](https://github.com/user-attachments/assets/ec2940ff-e589-42a1-9fd9-354991ea19d3)
      ![image](https://github.com/user-attachments/assets/d487f7ee-2ad1-47ab-922f-dfa9df073ee9)
      ![image](https://github.com/user-attachments/assets/7e7f9fee-a9b8-46d6-a38d-2a9dc4910bf7)

___
