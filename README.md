# ansible-CA-deployment
CA deployment with ansible

# Objective

Deploy an application behind a reverse proxy
```
Establish a chain of CA (certificate authority) 
-> create a public child certificate (for the reverse proxy) 
-> create a private child certificate (for the mTLS app <-> reverse proxy) 
```

# STEP

## part 1
1. install python
1. install ansible
2. create a folder
3. a role for certificates
    - a task for the root
        - generate the private key (RSA 4096)
        - generate the public key
            - create a CSR (certificate siging request)
            - sign the cert
    - a task for children
        - generate the private key (RSA 4096)
        - generate the public key
            - create a CSR (certificate siging request)
            - sign the cert
4. a playbook

## part 2
1. install docker
2. create the docker subnet
3. Create the reverse proxy
4. Create the dns server
    - including reverse proxy config
    - server config
    - basic DNS entries
5. Raise a monitoring stack
## usage
```
$ git clone https://github.com/MiroYld/ansible-CA-deployment.git
$ cd ansible-CA-deployment/
$ ansible-playbook --ask-vault-pass playbook.yml
pass => soleil123
```
