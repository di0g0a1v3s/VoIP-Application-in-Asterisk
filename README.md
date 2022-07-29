# VoIP-Application-in-Asterisk
 VoIP Application built with Asterisk and Python
 
## Instalation Instructions

#### Installing Asterisk
sudo apt-get update
sudo apt-get install asterisk

#### Copy files sip.conf and extensions.conf to the correct folder
sudo cp sip.conf /etc/asterisk
sudo cp extensions.conf /etc/asterisk

#### Copy sound files to the correct folder
sudo cp *.gsm /usr/share/asterisk/sounds

#### Install googlets text to speech interface
sudo apt install git
git clone git://github.com/zaf/asterisk-googletts
sudo cp asterisk-googletts/googletts.agi /usr/share/asterisk/agi-bin/
sudo chmod 777 /usr/share/asterisk/agi-bin/googletts.agi

#### Install sound packets sox and mpg123 required for the googlets interface
sudo apt-get install sox
sudo apt-get install mpg123

#### Copy the file postal_code.py to the correct directory
sudo cp postal_code.py /usr/share/asterisk/agi-bin
sudo chmod 777 /usr/share/asterisk/agi-bin/postal_code.py

#### Install packet python-pip, as well as necessary libraries as root
sudo apt install python-pip
sudo -i
pip install pyst2
pip install beautifulsoup4
pip install requests
pip install lxml
exit

#### Asterisk startup
sudo asterisk -vvvvr
reload
