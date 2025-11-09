FROM python:3.10.19

WORKDIR /app

RUN apt-get update

COPY . .

RUN echo "\
for i in range(10):\n\
    print(f'goodDF works')"> app.py

CMD ["python", "app.py"]