FROM python:3.12-alpine

COPY requirements.txt ./
RUN pip install -r requirements.txt

COPY cli_9999.py ./
ENTRYPOINT ["python", "./cli_9999.py"]
CMD ["--url=http://host.docker.internal:9999" ]
