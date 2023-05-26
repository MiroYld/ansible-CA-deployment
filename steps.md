# Objectif

Déployer une application derrière un reverse proxy
Etablir une chaine de CA (certificate authority)
-> créer un certificat enfant public (pour le reverse proxy)
-> créer un certificat enfant privé (pour le mTLS app <-> reverse proxy)


sudo sysctl net.ipv4.ip_unprivileged_port_start=53


# STEPS !!!

1. avoir un env
1. installer python
1. installer ansible
2. créer un dossier
3. un role pour les certificats
    - un tasks pour le root
        - générer la clé privée (RSA 4096)
        - générer la clé publique
            - créer un CSR (certificate siging request)
            - signer le cert
    - un task pour les enfants
        - générer la clé privée (RSA 4096)
        - générer la clé publique
            - créer un CSR (certificate siging request)
            - signer le cert
4. un playbook


1. installer docker
2. créer le subnet docker
3. Créer le reverse proxy
4. Créer le serveur dns
    - dont config reverse proxy
    - config du serveur
    - entrées DNS de bases
5. Lever une stack de monitoring
