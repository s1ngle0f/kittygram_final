FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir

RUN pip install python-decouple

COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:9000", "kittygram_backend.wsgi"]

RUN python manage.py collectstatic --noinput

#RUN python manage.py migrate
