# apiteam-season2-workshop-apigw-allinone

## Prerequisites 
* https://github.com/YasuhideKato/apiteam-season2-workshop-vagrant
```
cd apiteam-season2-workshop-apigw-allinone
you put license file and Edge Module apigee-edge-4.15.07.03.zip to this directory.
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
cd /opt/apigee4/bin
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
cd /opt/apigee4/bin
sudo ./all-status.sh
sudo ./all-stop.sh
sudo ./all-start.sh
exit
```

## API-GW Management UI
* http://192.168.33.10:9000
* username: admin@example.com
* passwowrd: secret123
* org: base
* env: prod

## API-GW API
If you will deploy somthing APIProxies, you can go
* http://192.168.33.10:9001/{basePath}/{resourcePath}

## API-GW BaaS Management UI
* http://192.168.33.20:9000
* username: admin@example.com
* passwowrd: secret123

## API-GW BaaS API
If you will set up something baas data, you can go  
* http://192.168.33.10.8081/AppServices/{org}/{app}

