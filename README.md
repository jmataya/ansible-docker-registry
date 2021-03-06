ansible-docker-registry
=======================

[![Build Status](https://travis-ci.org/nextrevision/ansible-docker-registry.png?branch=master)](https://travis-ci.org/nextrevision/ansible-docker-registry)

Ansible role for installing docker registry

## Variables

### Default

* ```domain```: Specify a domain name (default: ```localhost```)
* ```log_level```: Log level for the server (default: ```info```)
* ```secret_key```: Secret key used by the registry (default: ```cd8fbaa639122edad0617212ff0a6666```)
* ```storage_type```: Accepts either ```file``` or ```s3``` (default: ```file```)
* ```storage_path```: File path to store registry uploads (default: ```/mnt/registry```)
* ```manage_nginx```: Install nginx and manage docker-registry vhost (default: ```true```)
* ```manage_redis```: Install and manage redis server (default: ```true```)

### S3 Storage

* ```s3_region```: optional, will default to US Standard
* ```s3_bucket```: also provides the value for boto_bucket
* ```s3_storage_path```
* ```s3_access_key```
* ```s3_secret_key```

## Using with Docker

    docker pull busybox
    docker tag busybox 192.168.59.4:5000/busybox
    docker push 192.168.59.4:5000/busybox

## Testing

    rake vagrant

## TODO

* Add SSL support (requires valid cert)
* Add basic auth support (requires SSL)
* Extend config options
