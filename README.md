# minitel-wish-wizard
Wish Wizard system build with old French minitels

Wish Wizard 
"Make Dreams Come True"

Installation:
Linux oder Raspberry
benötigt: SSH zugriff & evtl VNC
mariadb  (und libmariadb-dev via sudo apt install)
python (sollte ja da sein, auf jeden Fal > 3.0)
mit pip 
und pip install mysql.connector

Programm benötigt aus mariadb:
CREATE DATABASE minitel
utilisateur1 : CREATE USER 'utilisateur1'@'%'
GRANT ALL ON *.* TO 'utilisateur1'@'%'
    
Tables: whishes , prefs
To delete (drop) table :
sudo mariadb
USE minitel
DROP TABLE wishes

Autostart via: 
minitelstart.service datei copy to /etc/systemd/system (check path in file)

sudo systemctl enable minitelstart.service
sudo systemctl daemon-reload

or "crontab -e" und "@reboot sleep 60 && cd /home/pi/minitel && /usr/bin/python /home/pi/minitel/wish_server_locV0.py"
oder
eventuel mit .desktop  (file im Verzeichniss)
Special codes: 
On pages Choices (1 or 2) :
99 to open delete whishes page
98 preferences (NOT READY YET)
