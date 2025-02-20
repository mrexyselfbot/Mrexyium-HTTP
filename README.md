# Mrexyium-HTTP
## Mrexyium-HTTP is a tool written in python to perform layer 7 stress test on your own server.

For CF bypass you'll need a proxy list with very good connection and low latency to your server.

*Third party proxy checker you may need:*
https://github.com/maxmalysh/python-proxy-checker

### Install:
```
apt-get update
apt-get -y upgrade
apt-get install build-essential nodejs python-setuptools python3-setuptools
apt-get install -y python3-pip
pip3 install PySocks requests cfscrape scapy-python3
```

### Run:
```
python3 cf_cannon.py www.abc.com -t 1000 -d /index.php
```

### Parameters:
```
-d --dir : path of target, I.e: www.abc.com/index.php then -d /index.php
-s --ssl : Use http or https. For https&proxy mode your proxy must support https.
-p --port: Port of the server,80 or 443?
-t --threads: How many threads?
-l --time: Haven't done yet
-x --proxy_file_location : Deafult: proxy.list, feel free to assign other list.
```
### Don't forget:
```
ulimit -n 655350
```
### Proof of Power
![image](https://levyhsu.com/wp-content/uploads/2018/10/webwxgetmsgimg.jpeg)

### Notice:
Each "ERROR:root:’http://abc.com’ returned an error. Could not collect tokens."
indicates one proxy failure (cfscrape can’t access page though server)
