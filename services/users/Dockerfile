FROM python:3.7.2-alpine

RUN apk update && \
apk add --virtual build-deps gcc python-dev musl-dev && \
apk add postgresql-dev && \
apk add netcat-openbsd

WORKDIR /usr/src/app

COPY ./requirement.txt /usr/src/app/requirement.txt
RUN pip install -r requirement.txt

COPY ./entrypoint.sh /usr/src/app/entrypoint.sh
RUN chmod 755 /usr/src/app/entrypoint.sh

COPY . /usr/src/app

CMD ["/usr/src/app/entrypoint.sh"]