FROM python:3.12-alpine

COPY requirements.txt ./
RUN pip install -r requirements.txt

COPY __init__.py ./
COPY true_agent_50001.py ./

EXPOSE 50001

CMD [ "python", "./true_agent_50001.py", "--host=host.docker.internal" ]
