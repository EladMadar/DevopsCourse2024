FROM python:latest
WORKDIR /app
COPY . /app
RUN pip install -e .
ENV FLASK_APP=flaskr
ENV FLASK_ENV=development
EXPOSE 5000
RUN flask init-db
CMD ["flask", "run", "--host=0.0.0.0"
