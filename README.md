# Grafana-Installation

How to install Grafana on EC2 Amazon Linux 2 Or Linux

EC2 Security Group Setup : Allow ssh and custom port 3000

Grafana Installation

Upgrade all packages

# sudo yum update -y

Then we add a new YUM repository for the operating system to know where to download Grafana. Use nano editor command to save the file

# sudo nano /etc/yum.repos.d/grafana.repo


Add the lines below to grafana.repo. This setting will install to the Open Source version of Grafana.  Use nano editor command to save the file
#--------------------------------------------------------------------

[grafana]

name=grafana

baseurl=https://packages.grafana.com/oss/rpm

repo_gpgcheck=1

enabled=1

gpgcheck=1

gpgkey=https://packages.grafana.com/gpg.key

sslverify=1

sslcacert=/etc/pki/tls/certs/ca-bundle.crt

#--------------------------------------------------------------------

Install Grafana

# sudo yum install grafana
# sudo systemctl daemon-reload
# sudo systemctl start grafana-server


Start the Grafana Server.

# sudo systemctl status grafana-server


Status output should show that grafana-server is active (running).

# sudo systemctl enable grafana-server.service


Testing Grafana

Visit the newly installed Grafana Server by visiting the Public IP of the EC2 Instance on port 3000.

18.206.59.38(publicIP):3000

See default username and password below.

Username

admin

Password

admin

