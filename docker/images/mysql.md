# MySQL

In my opinion, I prefer `mysql:8.0` than others.

# link
[mysql image](https://hub.docker.com/_/mysql)

# usage tips

## configurations

[mysql.cnf](../mysql/mysql.cnf)

## scripts

```bash
docker run -d -p 13306:3306 \
  --restart=always \
  --name mysql_test \
  -v /path/to/your/localdir:/var/lib/mysql \ 
  -v /path/to/your/mysql.cnf:/etc/my.cnf \
  -e MYSQL_ROOT_PASSWORD=123456 mysql:8.0
```

## compose(recommend) 

If you want to deploy a test mysql, you can use this compose.

```yml
version: '3.0'
services:
  db:
    image: mysql:8.0
    restart: always
    volumes:
      - /path/to/yourdir:/var/lib/mysql
      # if you have self defined configuration
      # - /path/to/your/mysql.cnf:/etc/my.cnf
    environment:
      # of course you can change
      # another strong password
      MYSQL_ROOT_PASSWORD: 123456
    ports:
      - 23306:3306
```
