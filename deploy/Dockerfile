FROM python:3.8

# set the working directory in the container
WORKDIR /code

# copy the dependencies file to the working directory
COPY requirements.txt .

RUN python -m pip install --upgrade pip
# install dependencies
RUN pip install -r requirements.txt

# copy the content of the local src directory to the working directory
COPY . .

RUN python manage.py migrate

# command to run on container start
#ENTRYPOINT ["python", "manage.py"]
#CMD ["runserver", "0.0.0.0:8000"]

CMD [ "python", "manage.py", "runserver", "0.0.0.0:8000"]

# sudo docker run --name test -p 8000:8000 todo-app:latest