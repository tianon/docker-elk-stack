# Docker ELK Stack

A simple `docker-compose.yml` to demo/test things in a _very_ simple ELK stack (NOT RECOMMENDED FOR ANY SERIOUS USE).

```console
$ docker-compose up -d
Creating elkstack_kibana_1
Creating elkstack_elasticsearch_1
Creating elkstack_logstash_1

$ # give logstash/elasticsearch a minute to initialize and be ready for incoming data

$ docker run --rm --log-driver gelf --log-opt gelf-address=udp://localhost:12201 alpine echo 'hello elk!'
hello elk!
```

Then, pull up http://localhost:5601 in a browser, set up an index, and check out the "Discover" tab for the `hello elk!` event we generated.
