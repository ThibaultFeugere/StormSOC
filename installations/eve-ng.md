# Doc d'installation 

## Installation Eve-ng

Pour installer eve-ng il faut tout d'abord aller sur le site et télécharger le .ova ou .iso selon nos préférence d'hyperviseur. 

Lors du premier démarrage le console prompt sera disponible et les identifiants par défaut sont : 
``` bash
root 
eve
```

une fois connecté on à plus qu'a suivre les instruction que la vm nous donne pour configurer le root password le dhcp et tout ce genre d'option.

une fois la configuration terminé la VM va redémarrer et tout sera prêt il faudra juste faire un petit 
```bash 
apt-get update 
apt-get install
```

pour appliquer les dernieres mises à jours 

## Ajouter une image Cisco IOL sur eve-ng 

Télécharger au préalable un .bin de l'iol que vous souhaitez installé puis ensuite il faudra se connecter à la vm en SCP pour uploader le fichier dans le répertoire ``/opt/unetlab/addons/iol/bin``

ensuite il faudra fixer les permissions avec la commande ``/opt/unetlab/wrappers/unl_wrapper -a fixpermissions``

par la suite il sera nécéssaire pour que les iol fonctionne bien avoir une licence, 

pour cela on peut utiliser un petit script python qui va nous aider à les générer, (il faut l'exécuter sur la vm Eve-ng dans le répertoire ``/opt/unetlab/addons/iol/bin``)
```python 

print("*********************************************************************")
print("Cisco IOU License Generator - Kal 2011, python port of 2006 C version")
print("Modified to work with python3 by c_d 2014")
import os
import socket
import hashlib
import struct

# get the host id and host name to calculate the hostkey
hostid=os.popen("hostid").read().strip()
hostname = socket.gethostname()
ioukey=int(hostid,16)
for x in hostname:
 ioukey = ioukey + ord(x)
print("hostid=" + hostid +", hostname="+ hostname + ", ioukey=" + hex(ioukey)[2:])

# create the license using md5sum
iouPad1 = b'\x4B\x58\x21\x81\x56\x7B\x0D\xF3\x21\x43\x9B\x7E\xAC\x1D\xE6\x8A'
iouPad2 = b'\x80' + 39*b'\0'
md5input=iouPad1 + iouPad2 + struct.pack('!i', ioukey) + iouPad1
iouLicense=hashlib.md5(md5input).hexdigest()[:16]

print("\nAdd the following text to ~/.iourc:")
print("[license]\n" + hostname + " = " + iouLicense + ";\n")
print("You can disable the phone home feature with something like:")
print(" echo '127.0.0.127 xml.cisco.com' >> /etc/hosts\n"
```

lorsque l'on éxécute le script il va nous donner un texte à coller dans le fichir iourc qu'il faudra créer avec un éditeur de texte 

## Ajout d'image linux sur Eve-ng

[Repo d'image linux](https://mega.nz/#F!y5YCwZCA!42_S__9wwPVO0zHIfC4xow)

Même principe que pour une image Cisco IOL, il faut se connecter en SCP pour l'upload dans le répertoire ```cd /opt/unetlab/addons/qemu/```

ensuite on fait un ```tar xzvf ``` de l'image 

et on peut ``rm -f `` l'image tar.gz 

ensuite on n'oublie pas de fix les permissions avec la commande ``/opt/unetlab/wrappers/unl_wrapper -a fixpermissions``
