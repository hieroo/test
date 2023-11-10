# FlaskNetworkBackup
A free open-source Flask app for backup on switches,routers and firewalls. 

## Features
*  Getting backup from Fortinet, Palo Alto, Cisco, Aruba, Dell Force10, Brocade ICX, Ruijie, Juniper, Huawei devices 
*  Creating a .cfg file and email the file as an attachment
*  Easy-to-use web interface
*  Add your device once and backup without re-enter again 
*  Store your email configuration, login data, backups on SQLite
*  Download configuration backup as cfg file 
*  Search devices and backups

## Prerequisites
> git 

`$ sudo apt install git`

> pip 
 
`$ sudo apt install python3-pip`

## Usage
`$ git clone https://github.com/diyarbagis/FlaskNetworkBackup.git`

`$ cd IST`

`$ pip install -r requirements.txt`

`$ python3 fnetbackup.py`

:rocket: **Open http://0.0.0.0:6565 on your browser and get your backup.**

## If you want to run the app as a service on your Linux server
#### Follow these instructions:
`$ sudo nano /etc/systemd/system/fnetbackup.service `

```bash
[Unit]
Description=Flask Network Backup Service
After=network.target

[Service]
User=<your_username>
WorkingDirectory=/path/to/file/location
Environment="PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games"
ExecStart=/usr/bin/python3 fnetbackup.py
Restart=always

[Install]
WantedBy=multi-user.target
```

> Make sure to replace <your_username> with your actual username, and /path/to/file/location with the path to file.


`$ sudo systemctl daemon-reload`

`$ sudo systemctl enable fnetbackup`

`$ sudo systemctl start fnetbackup`

:rocket: **http://0.0.0.0:6565 ready for you!**

**check status**

`$ sudo systemctl status fnetbackup`

## Screenshots











