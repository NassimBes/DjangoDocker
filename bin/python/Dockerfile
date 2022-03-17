FROM python:3.10
ENV PYTHONUNBUFFERED 1
RUN mkdir /code
WORKDIR /code
RUN pwd
ADD requirements.txt /code/
RUN pip3 install -r requirements.txt
RUN pip3 install https://projects.unbit.it/downloads/uwsgi-lts.tar.gz
RUN pip3 install mysqlclient

ADD . /code/
RUN cd /code/ && \
    python -m django startproject app .