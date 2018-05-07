## [Django Docker Compose](https://github.com/prakashsharmacs24/django-docker-compose)
The "Django Docker Compose" is a reference application created to show how

to develop Django based application using the docker and docker compose.

## Reference Documentation: [Official Docker Compose-Sample applications](https://docs.docker.com/compose/django/)


## Maintained by: [Prakash Kumar](https://github.com/prakashsharmacs24)



## Built With
* [Django](http://www.celeryproject.org/) - The web framework used
* [Postgresql](https://postgresql.org/) - Relational Database

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them
[![Deploy](https://hub.docker.com/public/images/logos/mini-logo.svg)](https://docs.docker.com/compose/django/)
```
Docker version 18.03.1-ce, build 9ee9f40
docker-compose version 1.21.1, build 7641a569,
```


How to use this image
------------

Run Application with a Docker/Docker-Compose
------------
This is the recommended way to run application. You can use the following docker compose template:
```yaml
version: '3'

services:
  db:
    image: postgres
  web:
    build: .
    command: python3 manage.py runserver 0.0.0.0:8000
    volumes:
      - .:/code
    ports:
      - "8000:8000"
    depends_on:
      - db

```


Execute this command to install the project:
1.  Clone the project repository
```bash
git clone --depth=1 https://github.com/prakashsharmacs24/django-docker-compose
cd django-docker-compose
```

2.  Builds the images define in the docker-compose.yml
```bash
docker-compose build
```

3.  Create your containers


```bash
docker-compose up -d
```
4.  Make  Migration


```bash
docker-compose run web python manage.py makemigrations
docker-compose run web python manage.py migrate
```
5.  Start New Application


```bash
docker-compose run web python manage.py startapp demo_app
```

6. Close Docker container
When you’re done, don’t forget to close down your Docker container.
```bash
docker-compose down
```
# License

MIT License

Copyright (c) 2018 prakashkumar(<mailto:prakashsharmacs24@gmail.com>)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
