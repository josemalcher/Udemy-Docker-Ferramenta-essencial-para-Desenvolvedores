## <a name="parte4"> Seção: 4 - Uso Básico do Docker</a>

### 21. Meu querido amigo run

```bash
$ docker container run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete
Digest: sha256:10d7d58d5ebd2a652f4d93fdd86da8f265f5318c6a73cc5b6a9798ff6d2b2e67
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

```

### 22 Ferramentas diferentes

```bash
$ docker container run debian bash --version
Unable to find image 'debian:latest' locally
latest: Pulling from library/debian
dbba69284b27: Pull complete
Digest: sha256:87eefc7c15610cca61db5c0fd280911c6a737c0680d807432c0bd80cd0cca39b
Status: Downloaded newer image for debian:latest
GNU bash, version 5.1.4(1)-release (x86_64-pc-linux-gnu)
Copyright (C) 2020 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>

This is free software; you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

```

```bash
$ docker container ps -a
CONTAINER ID   IMAGE         COMMAND            CREATED              STATUS                          PORTS     NAMES
66f5aba3f41a   debian        "bash --version"   About a minute ago   Exited (0) About a minute ago             musing_wright
13db19c71696   hello-world   "/hello"           16 minutes ago       Exited (0) 16 minutes ago                 serene_agnesi

```

--rm apaga o container depois de executado.

```bash
$ docker container run --rm debian bash --version
GNU bash, version 5.1.4(1)-release (x86_64-pc-linux-gnu)
Copyright (C) 2020 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>

This is free software; you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.


$ docker container ps -a
CONTAINER ID   IMAGE         COMMAND            CREATED          STATUS                      PORTS     NAMES
66f5aba3f41a   debian        "bash --version"   3 minutes ago    Exited (0) 3 minutes ago              musing_wright
13db19c71696   hello-world   "/hello"           18 minutes ago   Exited (0) 18 minutes ago             serene_agnesi
```

### 23 Run cria sempre novos containers

```bash
$ docker container run -it debian bash
root@b553919768f1:/# touch curso-docker.txt
root@b553919768f1:/# ls
bin  boot  curso-docker.txt  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@b553919768f1:/# ls curso-docker.txt 
curso-docker.txt
root@b553919768f1:/# exit
exit


$ docker container run -it debian bash
root@7015d51a516a:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@7015d51a516a:/#

```

```bash
$ docker ps -a
CONTAINER ID   IMAGE         COMMAND            CREATED              STATUS                      PORTS     NAMES
7015d51a516a   debian        "bash"             47 seconds ago       Exited (0) 11 seconds ago             happy_williamson
b553919768f1   debian        "bash"             About a minute ago   Exited (0) 51 seconds ago             eloquent_dewdney
bbf2781e1bef   debian        "-it"              About a minute ago   Created                               modest_sanderson
66f5aba3f41a   debian        "bash --version"   7 minutes ago        Exited (0) 7 minutes ago              musing_wright
13db19c71696   hello-world   "/hello"           23 minutes ago       Exited (0) 23 minutes ago             serene_agnesi

```


### 24 Containers devem ter nomes únicos

```bash
$ docker container run --name mydeb -it debian bash
root@667aef1d7eca:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@667aef1d7eca:/# exit
exit

$ docker container run --name mydeb -it debian bash
docker: Error response from daemon: Conflict. The container name "/mydeb" is already in use by container "667aef1d7eca06d5abfa6". 
You have to remove (or rename) that container to be able to reuse that name.
See 'docker run --help'.
```


### 25 Reutilizar containers

```bash
$ docker container ls -a
CONTAINER ID   IMAGE         COMMAND            CREATED          STATUS                      PORTS     NAMES
667aef1d7eca   debian        "bash"             2 minutes ago    Exited (0) 2 minutes ago              mydeb
8003fec14def   debian        "bash --version"   14 minutes ago   Exited (0) 14 minutes ago             frosty_goldberg
151b88e88997   hello-world   "/hello"           18 minutes ago   Exited (0) 18 minutes ago             focused_yonath

$ docker container start -ai mydeb
root@667aef1d7eca:/# touch /curso-docker.txt
root@667aef1d7eca:/# ls
bin  boot  curso-docker.txt  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

$ docker container start -ai mydeb
root@667aef1d7eca:/# ls
bin  boot  curso-docker.txt  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@667aef1d7eca:/#

```

### 26 Cego, surdo e mudo, só que não!

### 27 Aviso sobre comando no Windows

### 28 Mapear portas dos containers

### 29 Aviso sobre o comando pwd

### 30 Mapear diretórios para o container

### 31 Rodar um servidor web em background

### 32 Gerenciar o container em background

### 33 Manipulação de containers em modo daemon

### 34 Nova sintaxe do Docker Client
