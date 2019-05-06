FROM ubuntu:xenial

RUN apt-get update
RUN apt-get install -y \
                    python-setuptools \
                    python \
                    python-dev \
                    python-pip \
                    python2.7-dev \
                    python-software-properties \
                    libmysqlclient-dev

RUN pip install pipenv

COPY Pipfile .
COPY Pipfile.lock .

RUN pipenv install --system

COPY . .

CMD ["python", "manage.py", "runserver"]

