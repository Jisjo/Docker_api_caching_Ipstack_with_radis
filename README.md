# Docker_api_caching_Ipstack_with_radis
A simple program to fetch API requests from IPstack and caching using Radis Server. All the setup is containerized with Docker.


```
$ docker-compose up -d
Creating network "day-10_api-net" with the default driver
Creating network "day-10_default" with the default driver
Pulling caching_server (redis:alpine)...
alpine: Pulling from library/redis
59bf1c3509f3: Pull complete
719adce26c52: Pull complete
b8f35e378c31: Pull complete
d034517f789c: Pull complete
3772d4d76753: Pull complete
211a7f52febb: Pull complete
Digest: sha256:4bed291aa5efb9f0d77b76ff7d4ab71eee410962965d052552db1fb80576431d
Status: Downloaded newer image for redis:alpine
Pulling api_calling_server (fujikomalan/ipstack:v1)...
v1: Pulling from fujikomalan/ipstack
921b31ab772b: Pull complete
1a0c422ed526: Pull complete
ec0818a7bbe4: Pull complete
b53197ee35ff: Pull complete
8b25717b4dbf: Pull complete
2352f0e22307: Pull complete
0148c4900674: Pull complete
f2b28ffe4f9b: Pull complete
c5b6db6af2f3: Pull complete
Digest: sha256:db19eb2d4030d4fb34bcc9e385d9153646a6ed8d468fe4b60fcbe20a64fe65cd
Status: Downloaded newer image for fujikomalan/ipstack:v1
Creating ipstackapp   ... done
Creating radis-server ... done
```

```
$ docker container ls
CONTAINER ID   IMAGE                    COMMAND                  CREATED         STATUS         PORTS                                   NAMES
89f32a7aeabe   fujikomalan/ipstack:v1   "python3 app.py"         9 minutes ago   Up 9 minutes   0.0.0.0:80->8080/tcp, :::80->8080/tcp   ipstackapp
6651b68d8eaf   redis:alpine             "docker-entrypoint.s…"   9 minutes ago   Up 9 minutes   6379/tcp                                radis-server
```
> Test URL : http://<host_ip_addr>/1.1.1.1


![screenshot-result](https://github.com/Jisjo/Docker_api_caching_Ipstack_with_radis/blob/main/Screenshot.png)
