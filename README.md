# nfs-server
Juste un petit server NFS dans un docker pour faire des tests de montages persistants avec k8s par exemple
zf210524.1636


## Installation
Pour l'installation de Docker on peut exécuter le install.sh de ce dépôt:

https://github.com/zuzu59/docker_demo


### NAS server
Il n'y a rien à installer sauf le docker et le docker-compose


### NAS client
Si on veut tester le serveur NAS sur la machine du host du container Docker il faut installer un client NFS !
```
sudo apt update
sudo apt install -y nfs-common
mkdir nas_share
```


## Démarrage
Simplement faire:

```
./start.sh
```


## Tests du serveur NAS
On peut déjà voir s'il y a bien un *port* 2049 qui est ouvert sur le host avec:
```
netstat -nat |grep LIST
```

Simplement faire:
```
sudo mount 127.0.0.1:/ ./nas_share
```

Tout ce que l'on va écrire dans ./nas_share va se retrouver automatiquement dans ./nfs_share !

