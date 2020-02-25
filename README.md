[DCSS][DCSS] Web-tile Standalon Server Docker
=============================================
This is [Dungeon Crawl Stone Soup][DCSS] web-tile standalone server. If you try to make offical recode server please read this and support from IRC.

- [Setting up dgamelaunch and webtiles][1]
- [Freenode ##Crawl-dev chnnel][Crawl-dev]


Install
-------
Build from the dockerfile
```
$ git clone dfdgsdfg/DCSS-webtile-standalone-docker
$ cd DCSS-webtile-standalone-docker
$ sudo docker build --build-arg CRAWL_GIT_REPO=https://github.com/Hellmonk/hellcrawl --build-arg CRAWL_VERSION=0.21.1 -t crawl .
```

If no CRAWL_GIT_REPO is specified, it will default to 'https://github.com/crawl/crawl'.
If no CRAWL_VERSION is specified, it will default to 'master'.

Usage
-----
To spawn a new instance of DCSS on port 80. The -p 80:80 maps the internal docker port 80 to the outside port 80 of the host machine.

```
$ sudo docker run --name crawl -d -p 80:80 -v /Users/me/var/docker/crawl-data/:/data crawl
```

Start your newly created docker.

```
$ sudo docker start crawl
```

After starting the DCSS check to see if it started and the port mapping is correct. This will also report the port mapping between the docker container and the host machine.

```
$ sudo docker ps
0.0.0.0:80 -> 80/tcp crawl
```

You can the visit the following URL in a browser on your host machine to get started:

```
http://127.0.0.1
```



[DCSS]:http://crawl.develz.org/
[1]:https://crawl.develz.org/wiki/doku.php?id=setting_up_dgamelaunch_and_webtiles
[Crawl-dev]:http://webchat.freenode.net/?channels=%23%23crawl-dev
