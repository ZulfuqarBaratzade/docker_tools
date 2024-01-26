docker build -t my-postgres-image .

docker run -p 5432:5432 --name my-postgres-container -e POSTGRES_USER=myuser -e POSTGRES_PASSWORD=mypassword -e POSTGRES_DB=mydatabase -d my-postgres-image

docker-compose up -d