# dweomer/stunnel [![](https://badge.imagelayers.io/dweomer/stunnel:latest.svg)](https://imagelayers.io/?images=dweomer/stunnel:latest 'Get your own badge on imagelayers.io')

To secure an LDAP container named `directory`:

```
docker run -itd --name ldaps --link directory:ldap \ 
        -e STUNNEL_SERVICE=ldaps \
        -e STUNNEL_ACCEPT=636 \
        -e STUNNEL_CONNECT=ldap:389 \
        -p 636:636 \
#       -v /etc/ssl/private/server.key:/etc/stunnel/stunnel.key:ro \
#       -v /etc/ssl/private/server.crt:/etc/stunnel/stunnel.crt:ro \
    dweomer/stunnel
```
