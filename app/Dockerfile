FROM python:3.7-stretch
RUN apt update -y && apt install libpq-dev -y
WORKDIR /app
COPY ./requirements.txt ./
RUN pip install -r requirements.txt
COPY ./ ./
ENV DATABASE_URL=postgresql://postgres:postgres@postgres:5432/postgres
EXPOSE 8080
CMD ["uwsgi", "app.ini"]

