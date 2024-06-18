# Dockerfile
FROM python:3.12.3

WORKDIR /code

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY . /code

ENV PYTHONPATH=/code

RUN pip install psycopg2-binary

EXPOSE 8000

CMD [ "uvicorn", "main:app", "--proxy-headers", "--host", "0.0.0.0", "--port", "80" ]
