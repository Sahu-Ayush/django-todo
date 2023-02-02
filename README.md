# django-todo
A simple todo app built with django

![todo App](https://raw.githubusercontent.com/shreys7/django-todo/develop/staticfiles/todoApp.png)
### Setup
To get this repository, run the following command inside your git enabled terminal
```bash
$ git clone https://github.com/shreys7/django-todo.git
```
You will need django to be installed in you computer to run this app. Head over to https://www.djangoproject.com/download/ for the download guide

Once you have downloaded django, go to the cloned repo directory and run the following command

```bash
$ python manage.py makemigrations
```

This will create all the migrations file (database migrations) required to run this App.

Now, to apply this migrations run the following command
```bash
$ python manage.py migrate
```

One last step and then our todo App will be live. We need to create an admin user to run this App. On the terminal, type the following command and provide username, password and email for the admin user
```bash
$ python manage.py createsuperuser
```

That was pretty simple, right? Now let's make the App live. We just need to start the server now and then we can start using our simple todo App. Start the server by following command

```bash
$ python manage.py runserver
```

Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

Cheers and Happy Coding :)

To run docker
$ sudo docker build . -t todo-app
$ sudo docker run --name test -p 8000:8000 todo-app:latest

# Docker compose add:
build image using docker compose
$ sudo docker compose -f ./deploy/docker-compose.yml build

Check image which build by docker compose:
$ sudo docker image ls

Run the image
$ sudo docker run --name test -p 8000:8000 to-do-app-one:latest

```
[ayushsahu@ayush django-todo]$ sudo docker compose -f /deploy/docker-compose.yml build
stat /deploy/docker-compose.yml: no such file or directory
[ayushsahu@ayush django-todo]$ sudo docker compose -f ./deploy/docker-compose.yml build
[+] Building 81.3s (12/12) FINISHED                                                                                                     
 => [internal] load build definition from Dockerfile                                                                               0.1s
 => => transferring dockerfile: 690B                                                                                               0.0s
 => [internal] load .dockerignore                                                                                                  0.1s
 => => transferring context: 2B                                                                                                    0.0s
 => [internal] load metadata for docker.io/library/python:3.8                                                                      0.0s
 => [internal] load build context                                                                                                 69.2s
 => => transferring context: 40.39MB                                                                                              69.0s
 => [1/7] FROM docker.io/library/python:3.8                                                                                        0.3s
 => [2/7] WORKDIR /code                                                                                                            0.0s
 => [3/7] COPY requirements.txt .                                                                                                  0.1s
 => [4/7] RUN python -m pip install --upgrade pip                                                                                  4.4s
 => [5/7] RUN pip install -r requirements.txt                                                                                      5.4s
 => [6/7] COPY . .                                                                                                                 0.7s 
 => [7/7] RUN python manage.py migrate                                                                                             0.7s 
 => exporting to image                                                                                                             0.7s 
 => => exporting layers                                                                                                            0.7s 
 => => writing image sha256:ea8325d1fffdf5d766b09acd0dcc3724da0839907c3e505d2e371cd3ff4bd678                                       0.0s 
 => => naming to docker.io/library/to-do-app-one                                                                                   0.0s 

[ayushsahu@ayush django-todo]$ sudo docker image ls
REPOSITORY      TAG       IMAGE ID       CREATED          SIZE
to-do-app-one   latest    ea8325d1fffd   54 seconds ago   1.01GB
todo-app        latest    56bd2636ba41   19 hours ago     1.01GB
hello-world     latest    feb5d9fea6a5   16 months ago    13.3kB
[ayushsahu@ayush django-todo]$ sudo docker rm test
test
[ayushsahu@ayush django-todo]$ sudo docker run --name test -p 8000:8000 to-do-app-one:latest
Watching for file changes with StatReloader
System check identified some issues:

WARNINGS:
todos.Todo: (models.W042) Auto-created primary key used when not defining a primary key type, by default 'django.db.models.AutoField'.
        HINT: Configure the DEFAULT_AUTO_FIELD setting or the TodosConfig.default_auto_field attribute to point to a subclass of AutoField, e.g. 'django.db.models.BigAutoField'.

System check identified 1 issue (0 silenced).
[03/Feb/2023 01:29:06] "GET / HTTP/1.1" 302 0
[03/Feb/2023 01:29:06] "GET /todos/ HTTP/1.1" 200 3553
[03/Feb/2023 01:29:06] "GET /static/css/style.css HTTP/1.1" 304 0
[ayushsahu@ayush django-todo]$ 
```
