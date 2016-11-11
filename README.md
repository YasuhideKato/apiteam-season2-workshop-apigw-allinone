# apiteam-season2-workshop-apigw-allinone

## Prerequisites 
```
git clone https://github.com/YasuhideKato/apiteam-season2-workshop-vagrant.git
cd apiteam-season2-workshop-vagrant
cat README.md
```

## Getting Started
```
vagrant status
vagrant halt baas
vagrant ssh jump

# Silent Install && setup for apigw edge
cd /vagrant
ansible-playbook -vvv edge-aio.yml
[waint for minutes...]
exit

# Check for apigw edge
vagrant ssh edge
cd /opt/apigee/bin
sudo ./all-status.sh
sudo ./all-stop.sh
sudo ./all-start.sh

exit

vagrant up baas
vagrant ssh jump

# Silent Install && setup for apigw baas
cd /vagrant
ansible-playbook -vvv baas-aio.yml
[waint for minutes...]
exit

# Chceck for apigw baas
vagrant ssh baas
cd /opt/apigee/bin
sudo ./all-status.sh
sudo ./all-stop.sh
sudo ./all-start.sh
```


