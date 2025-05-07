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

# 3. Configurasi #
### 3.1. Setting Restic
abaikan, setingan langsung dari backrest
### 3.2. Setting RClone dan Backrest 
Pengaturan RClone dan Backrest sama seperti config di linux

```bash
rclone config
```

