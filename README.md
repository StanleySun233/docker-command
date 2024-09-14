# docker-command
Save my docker container

## 1. mysql 5.7
### for shell
```shell
docker run -p 3306:3306 --name mysql \
-v /mydata/mysql/log:/var/log/mysql \
-v /mydata/mysql/data:/var/lib/mysql \
--restart=always \
-e MYSQL_ROOT_PASSWORD=123456 \
-d mysql:5.7
```
### for cmd
```cmd
docker run -p 3306:3306 --name mysql -v /mydata/mysql/log:/var/log/mysql -v /mydata/mysql/data:/var/lib/mysql --restart=always -e MYSQL_ROOT_PASSWORD=123456 -d mysql:5.7
```

## 2. portainer
```shell
docker run -d -p 9000:9000 --restart=always --name portainer -v /var/run/docker.sock:/var/run/docker.sock -v /Users/lee/dev/docker_file/portainer/data:/data docker.io/portainer/portainer
```

## 3. redis
```shell
docker run --restart=always -p 6379:6379 --name redis -d redis:6.2.1  --requirepass pwd
```

## 4. minio
```shell
docker run \
-p 9000:9000 \
-p 9090:9090 \
--net=host \
--name minio \
-d --restart=always \
-e "MINIO_ACCESS_KEY=minioadmin" \
-e "MINIO_SECRET_KEY=minioadmin" \
-v /opt/minio/data:/data \
-v /opt/minio/config:/root/.minio \
 minio/minio server \
/data --console-address ":9090" -address ":9000"
```
