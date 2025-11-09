FROM python:latest

ENV DB_User=admin
ENV DB_Password=passwrod

WORKDIR /app

RUN apt-get update && apt-get install -y vim curl ngi

COPY . .

RUN pip install flask

RUN echo "\
for i in range(10):\n\
    print('it works')"> app.py

CMD ["python", "app.py"]