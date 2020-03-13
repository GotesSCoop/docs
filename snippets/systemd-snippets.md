# Monitorització

Guia https://www.digitalocean.com/community/tutorials/how-to-use-journalctl-to-view-and-manipulate-systemd-logs

## Filtrar per dates:

```
journalctl --since "2015-01-10 17:15:00"
journalctl --since "2015-01-10" --until "2015-01-11 03:00"
journalctl --since yesterday --until "1 hour ago"
```

## Follow i tail

```
journalctl -f --since today
journalctl -n 10 -f --since today

```

## Per servei

```
journalctl -u nginx.service
journalctl -u nginx.service -u php-fpm.service --since today
```

## Per PID, UID, GID

```
journalctl _PID=8088
journalctl _UID=33 --since today
```


## Per PATH

```
journalctl /usr/bin/bash

```

## Missatges de Kernel

```
journalctl -f -k
journalctl -k -b -5 # cinquè boot anterior
journalctl -k -b # boot actual
```

## Stdout o json

```
journalclt --no-pager
journalctl -b -u nginx -o json

```

## Mostrar fitxer de configuració d'un servei

```
systemctl show -p FragmentPath <servei>
```

