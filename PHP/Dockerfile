FROM php:8.2-cli

WORKDIR /var/www/html

COPY . .

EXPOSE 8000

ENTRYPOINT [ "php", "-S", "0.0.0.0:8000"]

#index.php is supposed to be changing in it's life cycle.
#so instead of copying index.php in Dockerfile we can use docker volumes.
#docker run -d -p 8000:8000 -v "$PWD":/var/www/html --name <containername> <dockerimage>
#this help to mount index.php and will update when make changes locally to the container.