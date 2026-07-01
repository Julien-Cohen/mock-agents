FROM python:3.12-alpine

COPY requirements.txt ./
RUN pip install -r requirements.txt

COPY __init__.py ./
COPY false_agent_50002.py ./

EXPOSE 50002

CMD [ "python", "./false_agent_50002.py", "--host=host.docker.internal" ]
