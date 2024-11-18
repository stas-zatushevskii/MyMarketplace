FROM python:3.11

RUN apt-get update && apt-get install -y \
    libpq-dev \
    python3-dev \
    build-essential

WORKDIR /code
COPY requirements.txt .
RUN python3 -m pip install --upgrade pip \
    && pip3 install -r /code/requirements.txt --no-cache-dir
COPY . .
CMD gunicorn MyMarketplace.wsgi:application --bind 0.0.0.0:8000