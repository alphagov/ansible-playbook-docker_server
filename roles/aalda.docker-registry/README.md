ansible-docker-registry
=========

[![Build Status](https://travis-ci.org/codingbunch/ansible-docker-registry.png?branch=master)](https://travis-ci.org/codingbunch/ansible-docker-registry)

An Ansible role for installing a private Docker Registry

Requirements
------------

TODO

Role Variables
--------------

### Default

* ```domain```: Specify a domain name (default: ```localhost```)
* ```log_level```: Log level for the server (default: ```info```)
* ```storage_type```: Accepts either ```local``` or ```s3``` (default: ```local```)
* ```storage_path```: File path to store registry uploads (default: ```/var/docker-registry```)
* ```use_nginx```: Install Nginx and configure docker-registry vhost (default: ```true```)
* ```use_redis```: Install and configure Redis server as a cache (default: ```true```)

### SSL Settings
* ```registry_port```: Custom port to have nginx listen on (default: ```80```)
* ```registry_ssl```: Enable SSL on nginx (default: ```false```)
* ```registry_ssl_cert```: Specify a SSL certificate to use (default: ```/etc/ssl/certs/docker_registry.crt```)
* ```registry_ssl_key```: Specify a SSL key to use (default: ```/etc/ssl/private/docker_registry.key```)
* ```create_ssl_cert```: Create a self-signed certificate if ```registry_ssl_cert``` is not present on the system (default: ```true```)

### OpenSSL cert settings
* ```openssl_bits```: Bit length of the private key (default: ```2048```)
* ```openssl_countryName```: Country Code (default: ```ES```)
* ```openssl_stateOrProvinceName```: State or Province (default: ```Madrid```)
* ```openssl_localityName```: Locality name (default: ```Madrid```)
* ```openssl_organizationName```: Full company name (default: ```MyCompany```)
* ```openssl_organizationalUnitName```: Company sub-division or a product name (default: ```Docker Registry```)
* ```openssl_commonName```: Your domain name, or in case of wildcard certificates, use an astrisk, like this: *.mycompany.com (default: ```mycompany.com```)

### S3 Storage

* ```s3_region```: optional, will default to US Standard
* ```s3_bucket```: also provides the value for boto_bucket
* ```s3_storage_path```
* ```s3_access_key```
* ```s3_secret_key```

## Note on SSL

If using a self-signed certificate, or no SSL certificate for recent docker versions, you must start the docker daemon with ```--insecure-registry```.

For boot2docker, see https://github.com/boot2docker/boot2docker#insecure-registry.


Example Playbook
----------------

    - hosts: docker-registry
      roles:
         - { role: codingbunch.ansible-docker-registry }

License
-------

MIT

Author Information
------------------

CodingBunch
