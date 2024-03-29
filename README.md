# PHPCircleCI

How it Works
Docker builds an image containing the application in src/ and all of its dependencies by using the Dockerfile contained in this repository.

The Dockerfile tells docker to use the official PHP Docker image as the parent image.

The PHP image then uses the official Debian Jessie Docker image as its parent image.

Debian then uses the scratch image as its base image.

At this point, an image has been built which contains Apache, PHP and all of the OS dependencies and libraries required to serve a webpage written in PHP.

Finally, docker copies index.php inside this repository to the /var/www/html folder inside the image. This is the Apache web root directory.

Setup
Ensure you have Docker installed
git clone this repository
sudo docker build -t PHPCircleCI .
sudo docker run -p 80:80 PHPCircleCI
