# Simple Notes App
This is a simple notes app built with React and Django.

## Requirements
1. Python 3.9
2. Node.js
3. React

## Installation
1. Clone the repository
```
git clone https://github.com/LondheShubham153/django-notes-app.git
```

2. Build the app
```
docker build -t notes-app .
```

3. Run the app
```
docker run -d -p 8000:8000 notes-app:latest
```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`


While running the application need to do:
1) Copy the data from mynotes/build to /var/www/html
CMD : cd mynotes/build
CMD : cp -rv * /var/www/html --------this will help to run the application because in this file have css, js, media and other.

2) Need to add the ip in /etc/nginx/sites-enabled .
   here will get default file in this file we are going to do some changes.
   CMD : sudo vim default  (REMINDER : without sudo you are not able to do changes.)
   in location add
   proxy_pass http://127.0.0.1:8000;
3) Now in same file
first uncomment the 2nd location and add
proxy_pass http://127.0.0.1:8000/api; -----------this will allow to run the backend and then in this app your data will start to store.
   
