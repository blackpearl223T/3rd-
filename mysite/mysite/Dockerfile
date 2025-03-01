# syntax=docker/dockerfile:1.4

 FROM --platform=$BUILDPLATFORM python:3.10-apine AS builder

EXPOSE 8000
WORKDIR /app

RUN apk update
RUN apk add \
    pkgconfig \
    gcc \
    musl-dev\
    bash \
    mariadb-dev

COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

COPY . /app

ENTRYPOINT { "python" }
CMD {"manage.py", "runserver", "0.0.0.0.8000"}