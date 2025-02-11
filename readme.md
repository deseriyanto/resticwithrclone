## Install Restic  dan Rclone

```
apt -y update
apt -y install restic rclone
```

## Install Backrest
Untuk install backrest bisa ikuti panduan dari situs GitHub [BackRest](https://github.com/garethgeorge/backrest)

## Configurasi Rclone ke WebDav Nextcloud
```
rclone config
```
selanjutnya ikuti arahan 

```bash
$ rclone config
```
pilih new dengan tekan N
```
No remotes found - make a new one
n) New remote
s) Set configuration password
q) Quit config
n/s/q> n
```
berikan nama `desbox`
```
name> desbox
```
pilih type storage , disini kita gunakan `Webdav` tekan `31`
```
Type of storage to configure.
Enter a string value. Press Enter for the default ("").
Choose a number from below, or type in your own value
 1 / 1Fichier
   \ "fichier"
...
31 / Webdav
   \ "webdav"
...
35 / seafile
   \ "seafile"
Storage> 31
```
kita diminta masukkan url dari WebDav
```
** See help for webdav backend at: https://rclone.org/webdav/ **

URL of http host to connect to
Enter a string value. Press Enter for the default ("").
Choose a number from below, or type in your own value
 1 / Connect to example.com
   \ "https://example.com"
url> https://desbox.desnet.id/remote.php/dav/files/eriyanto
```
Nama Service dari WebDav kita pilih Nextcloud
```
Name of the Webdav site/service/software you are using
Enter a string value. Press Enter for the default ("").
Choose a number from below, or type in your own value
 1 / Nextcloud
   \ "nextcloud"
 2 / Owncloud
   \ "owncloud"
vendor> 1
```
Selanjutnya masukkan Username

```
User name
Enter a string value. Press Enter for the default ("").
user> eriyanto
```
Sekarang kita diminta masukkan Password
```
Password.
y) Yes type in my own password
g) Generate random password
n) No leave this optional password blank (default)
y/g/n> y
Enter the password:
password: 
Confirm the password: <masukkan password sekalilagi>
password: <masukkan password>
```
pada opsi token kita bisa lewati saja dan biarkan `default`
```
Bearer token instead of user/pass (eg a Macaroon)
Enter a string value. Press Enter for the default ("").
bearer_token>
Edit advanced config? (y/n)
y) Yes
n) No (default)
y/n> n
```

Ringkasan configurasi yang telah kita buat sperti berikut
```
Remote config
--------------------
[desbox]
url = https://desbox.desnet.id/remote.php/dav/files/eriyanto
vendor = nextcloud
user = eriyanto
pass = *** ENCRYPTED ***
--------------------
y) Yes this is OK (default)
e) Edit this remote
d) Delete this remote
y/e/d> y
Current remotes:

Name                 Type
====                 ====
desbox               webdav

e) Edit existing remote
n) New remote
d) Delete remote
r) Rename remote
c) Copy remote
s) Set configuration password
q) Quit config
e/n/d/r/c/s/q> q

```

Selesai, kita bisa test cek isi folder menggunakan command berikut
```
rclone ls desbox:/
```

