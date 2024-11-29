# ACIT-2420-Assignment-3
ACIT 2420 Assignment 3 part 1


## Task 1

### creatting the 'webgen' user with the home directory '/var/lib/' with no login. 

```
sudo useradd -r -m -d /var/lib/webgen -s /usr/bin/nologin webge 
```
Move the cloned repo files to the webgen users directory.

this is how I did it:

```
 sudo mv /home/arch/2420-as3-p2-start/generate_index /var/lib/webgen/bin
 ```




## Task 2

Go into the terminal and make your service file using a text editor.

```
sudo nvim /etc/systemd/system/generate-index.service
```

Write your service file so that it runs at 5:00 every day, only when the network goes online, while specifying the webgen user and its group.

Here is my generate-index.service script:

```
[Unit]
After=network-online.target

[Timer]
OnCalendar=*_*_* 5:00:00
Persistent=true

[Service]
Type=simple
ExecStart=/var/lib/webgen/bin/generate_index
User=webgen
WorkingDirectory=/var/lib/webgen

[Install]
WantedBy=timers.target
```