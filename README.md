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
docker run -d -p 8005:9000 \
  --restart=always \
  --name portainer \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v /home/sjsun/docker/portainer/data:/data \
  docker.io/portainer/portainer
```

## 3. redis
```shell
docker run --restart=always -p 6379:6379 --name redis -d redis:6.2.1  --requirepass pwd
```

## 4. minio
```shell
docker run --name minio -d \
  --restart=always \
  -p 9000:9000 -p 9090:9090 \
  -e MINIO_ROOT_USER=minioadmin \
  -e MINIO_ROOT_PASSWORD=minioadmin \
  minio/minio server /data --console-address ":9090" --address ":9000"
```
## 5. webssh
```shell
docker run -d  --net host --log-driver json-file --log-opt max-file=1 --log-opt max-size=100m --restart always --name webssh -e TZ=Asia/Shanghai -esavePass=true jrohy/webssh
```
