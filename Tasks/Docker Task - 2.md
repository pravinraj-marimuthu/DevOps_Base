## Task Description

1. Create a dockerfile, docker-compose file which when executed must display your basic details in the website.

   ```
   mkdir /my-html-page
   cd my-html-page/
   vi index.html
   vi Dockerfile
   docker build -t mywebpage .
   docker run -d -p 80:80 mywebpage
   ```
   ![image](https://github.com/user-attachments/assets/033075fd-4fbe-44b4-9b3b-85ec4fa094bd)

#### index.html

```
<!doctype html>
<html>
  <head>
    <title>Know me - Poppins</title>
    <style>
      body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
        font-family: 'Poppins', sans-serif;
        background-color: #f0f0f0;
      }
      div {
        background-color: #ffffff;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        text-align: center;
      }
      p {
        margin: 15px 0;
        color: #333;
      }
      strong {
        font-family: 'Poppins', sans-serif;
        color: #555;
        font-weight: bold;
      }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
  </head>
  <body>
    <div>
      <p><strong>Name - </strong>I'm Pravinraj Marimuthu</p>
      <p><strong>Role - </strong>DevOps Engineer</p>
      <p><strong>Origin - </strong>Tamil, India</p>
    </div>
  </body>
</html>
```

#### Dockerfile
```

FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80
```

##### Dockerfile building the Docker image

![image](https://github.com/user-attachments/assets/176a7d33-ef86-4bf7-bb9b-381f51b940c4)

##### Docker image spins up a container 

![image](https://github.com/user-attachments/assets/cfac47cd-05f7-4f85-be7c-fecb0d959d13)

##### Container is running and HTML page is serving and open via Port 80

![image](https://github.com/user-attachments/assets/34790d8f-c062-42eb-b28b-757ffd676a3f)

##### Static website served by Docker container

![image](https://github.com/user-attachments/assets/c820543d-66c1-4b58-b6f3-6c4756c15bcb)
