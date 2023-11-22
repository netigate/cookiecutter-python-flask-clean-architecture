FROM python:3.11
EXPOSE 443
EXPOSE 9090
EXPOSE 8080
WORKDIR /code

RUN pip install -U pip \
    && apt-get update \
    && apt-get install libpq-dev -yq \
    && apt-get -y install libc-dev \
    && pip install poetry

RUN apt-get -yq install git

# -u is to see output in console
CMD ["poetry", "run", "python", "-u", "./src/app/manage.py", "grpcserver", "--port", "443"]