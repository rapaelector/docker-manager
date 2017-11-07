# AWS ELK Bitnami + Yelp's ElastAlert Service

## Installing ElastAlert
To setup on an AWS Bitnami ELK Stack EC2 Instance, do the following:

```bash
python --version
cd /opt/bitnami/apps
sudo apt-get install git software-properties-common python python-pip -y
sudo apt-get install python-dev libffi-dev libssl-dev -y
sudo pip install virtualenv
sudo pip install "setuptools>=11.3"
sudo git clone https://github.com/Yelp/elastalert.git
virtualenv elastalert
cd elastalert
sudo sh -c ". bin/activate; python setup.py install"
sudo -H sh -c ". bin/activate; pip install 'elasticsearch>=5.0.0'"
```

Elastalert should now be installed.

##Configuration
You will notice a config.yaml.sample file, use it if you want but elastalert expects simply config.yaml. By default,
it looks for rules in the example_rules directory.

## ElasticSearch Index Creation
```bash
bin/elastalert-create-index
```

## Testing Your Rules
Elastalert has an executable to test your rules:
```bash
bin/elastalert-test-rule example_rules/example_frequency.yaml
```

## Validate from Console
```bash
bin/elastalert --config config.yaml --verbose
```

## Running as a service

```bash
sudo wget https://raw.githubusercontent.com/fabianlee/blogcode/master/elastalert -O /etc/init.d/elastalert
sudo chmod 755 /etc/init.d/elastalert
sudo update-rc.d elastalert defaults 95 10
sudo vim /etc/init.d/elastalert

sudo useradd elastalert
sudo service elastalert status
sudo service elastalert start
```