# syntax=docker/dockerfile:1
FROM python:3.11-slim
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

ENV VIRTUAL_ENV=/opt/venv
RUN python -m venv $VIRTUAL_ENV
ENV PATH="$VIRTUAL_ENV/bin:$PATH"

WORKDIR /code

RUN apt-get update && \
    apt-get install -y libpq-dev gcc

COPY requirements.txt /code/    
RUN pip install -r requirements.txt

COPY . /code/
