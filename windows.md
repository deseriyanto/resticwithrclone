# 1. Install Scoop
Open a PowerShell terminal (version 5.1 or later) and from the PS C:\> prompt, run:
```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```
# 2. Install restic rclone dan backrest
### 2.1. Install restic ###
```
    scoop bucket add main
    scoop install main/restic
```

### 2.2. Install rclone ###
```
scoop install main/rclone
```

### 2.3. Install Backrest ###
```
scoop bucket add extras
scoop install extras/backrest
```

# 3. Rclone Configurasi #
Configurasi Rclone ke WebDav Nextcloud

3.1. Jalankan Config
```
rclone config
```
selanjutnya ikuti arahan 

```bash
$ rclone config
```
3.2. pilih new dengan tekan `n`
```
No remotes found - make a new one
n) New remote
s) Set configuration password
q) Quit config
n/s/q> n
```
3.3. berikan nama `desbox`
```
name> desbox
```
3.4. pilih type storage , disini kita gunakan `Webdav` tekan `31`
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
3.5. kita diminta masukkan url dari WebDav, `https://desbox.desnet.id/remote.php/dav/files/<usernamenextcloud>`
contoh : `https://desbox.desnet.id/remote.php/dav/files/eriyanto`
```
** See help for webdav backend at: https://rclone.org/webdav/ **

URL of http host to connect to
Enter a string value. Press Enter for the default ("").
Choose a number from below, or type in your own value
 1 / Connect to example.com
   \ "https://example.com"
url> https://desbox.desnet.id/remote.php/dav/files/eriyanto
```
3.6. Nama Service dari WebDav kita pilih `Nextcloud` masukkan angka `1`
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
3.7. Selanjutnya masukkan Username

```
User name
Enter a string value. Press Enter for the default ("").
user> eriyanto
```
3.8. Sekarang kita diminta masukkan Password
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
3.9. pada opsi token kita bisa lewati saja dan biarkan `default`
```
Bearer token instead of user/pass (eg a Macaroon)
Enter a string value. Press Enter for the default ("").
bearer_token>
Edit advanced config? (y/n)
y) Yes
n) No (default)
y/n> n
```

3.10. Ringkasan configurasi yang telah kita buat sperti berikut
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


Konfigurasi Rclone selesai, kita bisa test cek isi folder menggunakan command berikut
```
rclone ls desbox:/
```

# 4. Seting BackRest WebUI

Dashboard
![image](https://github.com/deseriyanto/resticwithrclone/blob/main/images/1.jpeg)

4.2. REPO
![image](https://github.com/deseriyanto/resticwithrclone/blob/main/images/2%20repo.jpeg)

4.3. PLAN JOB
![image](https://github.com/deseriyanto/resticwithrclone/blob/main/images/3.jpeg)

