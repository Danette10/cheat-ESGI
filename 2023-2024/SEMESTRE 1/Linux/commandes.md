# Liste des commandes Linux de base

## Sommaire

- [alias](#alias)
- [apt](#apt)
- [at](#at)
- [bash](#bash)
- [cat](#cat)
- [cd](#cd)
- [cheat](#cheat)
- [chmod](#chmod)
- [chown](#chown)
- [cp](#cp)
- [cut](#cut)
- [date](#date)
- [dd](#dd)
- [df](#df)
- [dhclient](#dhclient)
- [dpkg](#dpkg)
- [du](#du)
- [find](#find)
- [grep](#grep)
- [gzip](#gzip)
- [head](#head)
- [history](#history)
- [ip](#ip)
- [kill](#kill)
- [less](#less)
- [ln](#ln)
- [ls](#ls)
- [lsblk](#lsblk)
- [man](#man)
- [mkdir](#mkdir)
- [more](#more)
- [mount](#mount)
- [mv](#mv)
- [netstat](#netstat)
- [ping](#ping)
- [ps](#ps)
- [pwd](#pwd)
- [rename](#rename)
- [rm](#rm)
- [rmdir](#rmdir)
- [scp](#scp)
- [shutdown](#shutdown)
- [sort](#sort)
- [ssh](#ssh)
- [ssh-copy-id](#ssh-copy-id)
- [ssh-keygen](#ssh-keygen)
- [su](#su)
- [sudo](#sudo)
- [systemctl](#systemctl)
- [systemd](#systemd)
- [tail](#tail)
- [tar](#tar)
- [touch](#touch)
- [tr](#tr)
- [tree](#tree)
- [uname](#uname)
- [uniq](#uniq)
- [unzip](#unzip)
- [wc](#wc)
- [wget](#wget)

## Commandes importantes

### `alias`
> Crée un alias pour une commande.
```bash
$ alias ll='ls -l'
$ ll
total 0
```

### `apt`
> Gestionnaire de paquets Debian.
```bash
$ apt install <package>
$ apt remove <package>
$ apt update
$ apt upgrade
```

### `at`
> Exécute une commande à une heure donnée.
```bash
$ at 10:00
at> echo "Hello"
at> <EOT>
job 1 at Thu Jan  1 10:00:00 1970
```

### `bash`
> Interpréteur de commandes.
```bash
$ bash script.sh
```

### `cat`
> Affiche le contenu d'un fichier.
```bash
$ cat file.txt
Hello
```

### `cd`
> Change le répertoire courant.
```bash
$ cd Documents
$ pwd
/home/user/Documents
```

### `cheat`
> Affiche une cheatsheet.
```bash
$ cheat -h
```

### `chmod`
> Change les permissions d'un fichier. Syntaxe : `chmod <permissions (ex: 755 ou +x)> <fichier>`
```bash
$ chmod 755 script.sh
```

### `chown`
> Change le propriétaire d'un fichier. Syntaxe : `chown <propriétaire> <fichier>`
```bash
$ chown user script.sh
```

### `cp`
> Copie un fichier. Syntaxe : `cp <fichier> <destination>`
```bash
$ cp script.sh script2.sh
```

### `cut`
> Coupe un fichier en colonnes. Syntaxe : `cut -d <délimiteur> -f <colonnes> <fichier>`
```bash
$ cut -d : -f 1,3 /etc/passwd
root:0
daemon:1
```

### `date`
> Affiche la date et l'heure.
```bash
$ date
Thu Jan  1 00:00:00 1970
```

### `dd`
> Copie un fichier. Syntaxe : `dd if=<fichier> of=<destination>`
```bash
$ dd if=file.txt of=file2.txt
```

### `df`
> Affiche l'espace disque disponible.
```bash
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
udev            1.9G     0  1.9G   0% /dev
tmpfs           388M  1.2M  387M   1% /run
/dev/sda1        19G  1.9G   17G  11% /
```

### `dhclient`
> Obtient une adresse IP via DHCP.
```bash
$ dhclient
```

### `dpkg`
> Gestionnaire de paquets Debian.
> Installation d'un paquet : `dpkg -i <package.deb>`
> Désinstallation d'un paquet : `dpkg -r <package>`
```bash
$ dpkg -i <package.deb>
$ dpkg -r <package>
```

### `du`
> Affiche l'espace disque utilisé par un fichier.
```bash
$ du -h file.txt
4.0K	file.txt
```

### `find`
> Recherche un fichier. Syntaxe : `find <répertoire> -name <nom du fichier>`
```bash
$ find /home/user -name file.txt
/home/user/file.txt
```

### `grep`
> Recherche une chaîne de caractères dans un fichier. Syntaxe : `grep <chaîne> <fichier>`
```bash
$ grep "Hello" file.txt
Hello
```

### `gzip`
> Compresse un fichier. Syntaxe : `gzip <fichier>`
```bash
$ gzip file.txt
```

### `head`
> Affiche les premières lignes d'un fichier. Syntaxe : `head -n <nombre de lignes> <fichier>`
```bash
$ head -n 2 file.txt
Hello
```

### `history`
> Affiche l'historique des commandes.
```bash
$ history
1  ls
2  cd Documents
3  pwd
```

### `ip`
> Affiche les informations sur les interfaces réseau.
```bash
$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
...
```

### `kill`
> Tue un processus. Syntaxe : `kill <PID>`
```bash
$ ps
  PID TTY          TIME CMD
 1234 pts/0    00:00:00 bash
 5678 pts/0    00:00:00 ps
$ kill 1234
```

### `less`
> Affiche le contenu d'un fichier.
```bash
$ less file.txt
Hello
```

### `ln`
> Crée un lien symbolique. Un lien symbolique est un raccourci vers un fichier. Syntaxe : `ln -s <fichier> <lien>`
```bash
$ ln -s file.txt file2.txt
```

### `ls`
> Liste les fichiers et répertoires du répertoire courant.
```bash
$ ls
Desktop Documents Downloads Music Pictures Public Templates Videos
```

### `lsblk`
> Affiche les périphériques de stockage.
```bash
$ lsblk
NAME   MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda      8:0    0   20G  0 disk
└─sda1   8:1    0   20G  0 part /
```

### `man`
> Affiche le manuel d'une commande ou autre.
```bash
$ man ls
```

### `mkdir`
> Crée un répertoire. Syntaxe : `mkdir <répertoire>`
```bash
$ mkdir Documents
```

### `more`
> Affiche le contenu d'un fichier.
```bash
$ more file.txt
Hello
```

### `mount`
> Monte un périphérique de stockage. Syntaxe : `mount <périphérique> <point de montage>`
```bash
$ mount /dev/sdb1 /mnt
```

### `mv`
> Déplace un fichier. Syntaxe : `mv <fichier> <destination>`
```bash
$ mv file.txt Documents/
```

### `netstat`
> Affiche les connexions réseau.
```bash
$ netstat -tulpn
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0
```

### `ping`
> Envoie des paquets ICMP à une adresse IP.
```bash
$ ping
```

### `ps`
> Affiche les processus.
```bash
$ ps
  PID TTY          TIME CMD
 1234 pts/0    00:00:00 bash
 5678 pts/0    00:00:00 ps
```

### `pwd`
> Affiche le chemin du répertoire courant.
```bash
$ pwd
/home/user
```

### `rename`
> Renomme un fichier. Syntaxe : `rename <ancien nom> <nouveau nom>`
```bash
$ rename file.txt file2.txt
```

### `rm`
> Supprime un fichier. Syntaxe : `rm <fichier>`
```bash
$ rm file.txt
```

### `rmdir`
> Supprime un répertoire. Syntaxe : `rmdir <répertoire>`
```bash
$ rmdir Documents
```

### `scp`
> Copie un fichier via SSH. Syntaxe : `scp <fichier> <destination>`
```bash
$ scp file.txt user@
```

### `shutdown`
> Éteint le système.
```bash
$ shutdown -h now
```

### `sort`
> Trie les lignes d'un fichier. Syntaxe : `sort <fichier>`
```bash
$ sort file.txt
Hello
```

### `ssh`
> Se connecte à un serveur via SSH. Syntaxe : `ssh <utilisateur>@<adresse IP>`
```bash
$ ssh user@10.10.10.10
```

### `ssh-copy-id`
> Copie la clé SSH sur un serveur. Syntaxe : `ssh-copy-id <utilisateur>@<adresse IP>`
```bash
$ ssh-copy-id user@10.10.10.10
```

### `ssh-keygen`
> Génère une clé SSH. Syntaxe : `ssh-keygen`
```bash
$ ssh-keygen
```

### `su`
> Change d'utilisateur. Syntaxe : `su <utilisateur>`
```bash
$ su user
```

### `sudo`
> Exécute une commande en tant que super-utilisateur.
```bash
$ sudo apt install <package>
```

### `systemctl`
> Gestionnaire de services systemd.
> Démarrer, arrêter, redémarrer un service : `systemctl <start|stop|restart> <service>`
```bash
$ systemctl start <service>
$ systemctl stop <service>
$ systemctl restart <service>
$ systemctl status <service>
```

### `systemd`
> Gestionnaire de services systemd.
> Démarrer, arrêter, redémarrer un service : `systemctl <start|stop|restart> <service>`
```bash
$ systemd start <service>
$ systemd stop <service>
$ systemd restart <service>
$ systemd status <service>
```

### `tail`
> Affiche les dernières lignes d'un fichier. Syntaxe : `tail -n <nombre de lignes> <fichier>`
```bash
$ tail -n 2 file.txt
Hello
```

### `tar`
> Archive un fichier. Syntaxe : `tar -cvf <archive.tar> <fichier>`
```bash
$ tar -cvf archive.tar file.txt
```

### `touch`
> Crée un fichier. Syntaxe : `touch <fichier>`
```bash
$ touch file.txt
```

### `tr`
> Remplace un caractère par un autre. Syntaxe : `tr <caractère à remplacer> <caractère de remplacement> <fichier>`
```bash
$ tr 'a' 'b' file.txt
Hello
```

### `tree`
> Affiche l'arborescence d'un répertoire.
```bash
$ tree
.
├── Desktop
├── Documents
├── Downloads
├── Music
├── Pictures
├── Public
├── Templates
└── Videos
```

### `uname`
> Affiche des informations sur le système.
```bash
$ uname -a
Linux kali 5.10.0-kali7-amd64 #1 SMP Debian 5.10.28-1kali1 (2021-04-12) x86_64 GNU/Linux
```

### `uniq`
> Supprime les lignes en double. Syntaxe : `uniq <fichier>`
```bash
$ uniq file.txt
Hello
```

### `unzip`
> Décompresse un fichier. Syntaxe : `unzip <fichier.zip>`
```bash
$ unzip archive.zip
```

### `wc`
> Compte le nombre de lignes, de mots et de caractères d'un fichier. Syntaxe : `wc <fichier>`
```bash
$ wc file.txt
1 1 6 file.txt
```

### `wget`
> Télécharge un fichier. Syntaxe : `wget <URL>`
```bash
$ wget https://example.com/file.txt
```