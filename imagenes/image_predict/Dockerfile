FROM tiangolo/uvicorn-gunicorn-fastapi:python3.8-slim

WORKDIR /app

COPY ./requirements.txt ./requirements.txt
RUN pip3 install -r requirements.txt

EXPOSE 8200

RUN chmod -R -f 777 /app
USER 1000

COPY . .

ENTRYPOINT gunicorn --bind :8200 --workers 2 main:app --worker-class uvicorn.workers.UvicornH11Worker --preload --timeout 60 --worker-tmp-dir /dev/shm


