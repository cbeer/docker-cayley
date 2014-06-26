# Dockerized instance of Cayley
-------------------------------

https://github.com/google/cayley

By default, this will expose Cayley's HTTP endpoint against a leveldb instance. You can also run this against a mounted volume or a linked mongodb server.

Using Leveldb:

```
    $ docker run -v `pwd`/cayley-data:/mnt/cayley-data "cbeer/cayley" init --db=leveldb --dbpath=/mnt/cayley-data
    $ docker run -it -P -v `pwd`/cayley-data:/mnt/cayley-data "cbeer/cayley" http --db=leveldb --dbpath=/mnt/cayley-data
```

or Mongodb:

```
    $ docker run"cbeer/cayley" init --db=mongodb --dbpath=some-mongo-host.possibly-linked.local:27017
    $ docker run -it -P "cbeer/cayley" http --db=mongodb --dbpath=some-mongo-host.possibly-linked.local:27017
```
