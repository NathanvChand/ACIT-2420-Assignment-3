# ACIT-2420-Assignment-3
ACIT 2420 Assignment 3 part 1


## Task 1

### creatting the 'webgen' user with the home directory '/var/lib/' with no login. 

```
sudo useradd -r -m -d /var/lib/webgen -s /usr/bin/nologin webge 
```

## Task 2

Go into the terminal and make your service file using a text editor.

```
sudo nvim /etc/systemd/system/generate-index.service
```

