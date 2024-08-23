## Task Description

Create a custom docker image for nginx and deploy it using docker compose, where the volume bind mount should be at /var/opt/nginx location. Push the created custom docker image to your docker-hub.

```
mkdir custom_nginx
cd custom_nginx
cat index.html
```
index.html
```
[ec2-user@ip-172-31-40-22 custom_nginx]$ cat index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to Nginx</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        h1 {
            color: #4CAF50;
        }
    </style>
</head>
<body>
    <h1>Hello World!</h1>
    <p>Be happy :)</p>
    <p>       - Pravin :)</p>
</body>
</html>
```
Dockerfile
```
FROM nginx:latest

COPY index.html /usr/share/nginx/html/index.html
```
Docker-compose.yml
```
version: '3'
services:
  nginx:
    image: pravinrajmarimuthu/custom_nginx
    ports:
      - "80:80"
    volumes:
      - ./html:/var/opt/nginx
```
```
docker build -t pravinrajmarimuthu/custom_nginx .
```
![image](https://github.com/user-attachments/assets/9f26cdcd-bc19-4134-9716-65e37172cc0f)

```
docker login
docker push pravinrajmarimuthu/custom_nginx
```
![image](https://github.com/user-attachments/assets/37cc4046-3c81-4b61-a559-36d495b20d3e)
![image](https://github.com/user-attachments/assets/536730fa-50d9-47d4-a973-30073f580ae5)
![image](https://github.com/user-attachments/assets/f453a030-cf86-499d-963c-cb2b589b9199)
![image](https://github.com/user-attachments/assets/db73e5b2-ab40-41a9-a236-ea4248531764)




