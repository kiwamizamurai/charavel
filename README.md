## Preface
This is a first notebook on development with Laravel by layperson

## Check

- /src/public

this directory is for only check 

And, php container does not have laravel itself

You can git clone this repositoy then put your own laravel project into /src, removing /public

## Docker Usage

To generate the image data

- docker-compose build

To start up containers

- docker-compose up -d

To restart

- docker-compose restart

To reflect the changes in docker-compose.yml

- docker-compose up -d

To reflect the changes in Dockerfile

- docker-compose up -d build

To stop and remove (container network image)

- docker-compose down --rmi all

## Configuring

Open .env file in the src directory

DB\_HOST=mysql

> This name comes from the MySQL service we created in the docker-compose.yml file, and is used in the Docker network to reference the service from other containers.

APP\_URL=http://localhost:8080

> Add in the port number you’ve exposed in our nginx container to keep this pointing at a resolvable address.

## How to keep docker environment clean

To check disk usage

- docker system df

To get all system related info

- docker system info

To remove all unused data

- docker system prune

To remove specific unused data

- docker system prune -a --volumes
- docker image prune
- docker container prune
- docker voume prune
- docker network prune



## Memo

### nginx/default.conf

this is mostly a boilerplate nginx configuration used with most basic Laravel app

### php/php.ini

this is php setting file.
[mbstring] stands for multi-byte string.
[error\_reposrting] defines the desplaying the error
- https://qiita.com/shotets/items/3c95aef631b2c5eadae5

### Error

Once I run docker-copmose build command, Unfortunately a error occured.

- 404 error

### docker-compose.yaml

All containers will have the same network called laravel

[tty] keeps container running

[depends\_on] tells Docker that the php and mysql containers need to be running before nginx does

[volume] is for connection between local and container
For example,

> ./nginx/default.conf:/etc/nginx/conf.d/default.conf

The /nginx/default.conf file we created is linked to the /etc/nginx/conf.d/default.conf container file, and will give us the ability to modify the nginx web server on our local machine


## Vim practice

In this Laravel project, I'm going to practice Vim, So I will list up several shortcuts.

- [:bd] Deleting a buffer (tab is the way to desplay buffers)
- [/character] Find and Jump to the specific character
- [:noh] Remove specific word's highlighting
- [17G] Go to the line 17
- [G] Go to the last line of the document
- [H] Move to top of screen
- [M] Move to middle of screen
- [L] Move to end of screen
- [:wqa] Save and quit on all tabs


## Reference

about entire projet
- https://dev.to/aschmelyun/the-beauty-of-docker-for-local-laravel-development-13c0
- https://qiita.com/ucan-lab/items/56c9dc3cf2e6762672f4https://qiita.com/ucan-lab/items/56c9dc3cf2e6762672f4

about vim cheat sheet
- https://vim.rtorr.com/

about nginx
- https://qiita.com/nooboolean/items/7deeb9bd9823a8b92e09
- https://qiita.com/kotarella1110/items/3b0bd84fdb55276f37d9
