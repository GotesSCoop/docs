**Descarregar fitxer sense guardar per provar velocitat / conexió a intenret:**

```
tool fetch host=speed.hetzner.de url=http://speed.hetzner.de/100MB.bin keep-result=no
```

**Comprovació de IP de sortida de l'antena**

```
tool fetch host=whatismyip.akamai.com url=http://whatismyip.akamai.com/ dst-path=ip /file edit ip contents
```

o bé 

```
/tool fetch host=whatismyip.akamai.com url=http://whatismyip.akamai.com/ dst-path=ip; delay 1; :put [/file get ip contents]
```

**Prova de velocitat contra servidors públics de Mikrotik.**

Baixada

```
/tool bandwidth-test address=207.32.194.24 direction=receive user=btest password=btest protocol=tcp duration=10
```

Pujada

```
/tool bandwidth-test address=207.32.194.24 direction=transmit  user=btest password=btest protocol=tcp duration=10
```

**Esborrar claus ssh d'un key-owner (per quan n'hi ha moltes)**

```
/user ssh-keys remove [ /user ssh-keys find where key-owner=ansible@ofre ]

```
