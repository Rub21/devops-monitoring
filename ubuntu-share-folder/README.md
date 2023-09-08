# Ubuntu shared folder

- Samba (SMB)

```sh
sudo apt update
sudo apt install samba
echo "[shared_folder]
path = /home/kiara
read only = no
public = yes
writable = yes" | sudo tee -a /etc/samba/smb.conf > /dev/null
sudo smbpasswd -a kiara
# use same password as you OS user
sudo systemctl restart smbd
```

# Mac client

open in the browser: smb://192.168.1.95/shared_folder

**Note**: `192.168.1.95` is the ubuntu server IP

Connect with the user `kiara` and set the password
