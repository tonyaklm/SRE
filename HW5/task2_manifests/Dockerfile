FROM python:3.9-slim

WORKDIR .

RUN pip install prometheus-client

EXPOSE 8080
EXPOSE 8000

COPY /prometheus.py /prometheus.py

CMD ["python", "prometheus.py"]

