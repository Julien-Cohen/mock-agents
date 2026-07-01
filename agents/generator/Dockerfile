FROM python:3.12-alpine

COPY requirements.txt ./
RUN pip install -r requirements.txt

COPY __init__.py ./
COPY generator_agent_41241.py ./

EXPOSE 41241

CMD [ "python", "./generator_agent_41241.py", "--host=host.docker.internal" ]
