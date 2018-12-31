# Docker image for imxss
[![](https://images.microbadger.com/badges/image/zer0i3/imxss.svg)](https://microbadger.com/images/zer0i3/imxss ) [![](https://images.microbadger.com/badges/version/zer0i3/imxss.svg)](https://microbadger.com/images/zer0i3/imxss ) [![Build Status](https://travis-ci.org/zer0i3/imxss-docker.svg?branch=master)](https://travis-ci.org/zer0i3/imxss-docker)

imxss  is a xss platform, source code can be found [here](https://gitee.com/coodyer/imxss.git)

this only a docker image for imxss based on [tomcat8-mysql](https://hub.docker.com/r/zer0i3/tomcat8-mysql)

## Usage

Start a container:

```shell
docker run -itd -p 8080:8080 --env MYSQL_USER=user --env MYSQL_USER_PWD=password -v imxssdata:/var/lib/mysql zer0i3/imxss
```

Then access `http://your-ip:8080/install/install.jsp`  to init imxss

Or git clone this project then:

```shell
docker-compose up -d
```

Dockerfile in github: [imxss-docker](https://github.com/zer0i3/imxss-docker)