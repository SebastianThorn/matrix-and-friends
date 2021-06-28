# matrix-and-friends
This repo provides an easy way of installing components needed to run an isolated chat/im-platform.

Thing this repo will focus on completing:
- [ ] Simple way of installing with self-signed certificates
- [X] Simple way of installing with certificates from Let's Encrypt
- [ ] Simple way of installing with certificates from files

# Run ansible-playbook
```bash
ansible-playbook install.yaml -i vattenfart.se -uroot --diff -v
```

# Components
The repo creates a `docker-compose.yaml`-file that clues the needed components together.

## Synapse
This is the **on-premise** version of Matrix.

## Riot
This is the **on-premise** version of Element.io.

## Jitsi
This is a video-confrencing server, that is supported out of the box.

# Roles

## folders
Creates folders that is needed

## cert_selfsigned
Creates self-signed certificates, to get things rolling.

## cert_letsencrypt
Creates certificates from Let's Encrypt, you need a domain for this.

## cert_files
Moves files to correct locations, this assumes certificates on file.



# old doc
Don't mind thing below, then are only for my failing memory.



docker run -it --rm --mount type=volume,src=synapse-data,dst=/data \
  -e SYNAPSE_SERVER_NAME=example.org \
  -e SYNAPSE_REPORT_STATS=no matrixdotorg/synapse:v1.35.1 generate


matrixdotorg/synapse:v1.35.1


openssl req -newkey rsa:4096 \
            -x509 \
            -sha256 \
            -days 3650 \
            -nodes \
            -out nginx.crt \
            -keyout nginx.key

openssl req \
  -x509 \
  -nodes \
  -days 365 \
  -newkey rsa:4096 \
  -keyout /var/nginx-selfsigned.key \
  -out /var/nginx-selfsigned.crt \
  -subj '/CN=www.mydom.com/O=My Company Name LTD./C=US'



https://github.com/vector-im/element-web/releases/download/v1.7.30/element-v1.7.30.tar.gz


https://github.com/vector-im/element-web/blob/develop/docs/config.md


https://computingforgeeks.com/generate-openssl-self-signed-certificates-with-ansible/


https://www.digitalocean.com/community/tutorials/how-to-acquire-a-let-s-encrypt-certificate-using-ansible-on-ubuntu-18-04

