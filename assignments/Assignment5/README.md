sudo useradd -m neha 
sudo useradd -m vipul
sudo useradd -m abhishek
sudo groupadd linux
sudo groupadd sigma
sudo usermod -g sigma neha
sudo usermod -g sigma abhishek
sudo usermod -aG linux abhishek
sudo usermod -aG linux neha
sudo groupadd alpha
sudo useradd -m -G linux,alpha nikhil && sudo useradd -m -G linux,alpha priyashi

