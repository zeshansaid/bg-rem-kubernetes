FROM python:3.10-slim
# Install dependencies
RUN apt-get update && apt-get install -y 
RUN pip install --upgrade pip
COPY requirements.txt requirements.txt
RUN  pip install -r requirements.txt
ENV APP_HOME=/app
ENV PORT=8080
WORKDIR $APP_HOME
COPY . .
EXPOSE 8080
CMD exec gunicorn --bind :$PORT --workers 1 --threads 8 main:app
