# set

## ab
### CentOS
```
yum provides /usr/bin/ab
yum install -y httpd-tools
```

## apache kafka
Must use 2GB+  
```
wget http://mirror.cc.columbia.edu/pub/software/apache/kafka/0.10.0.1/kafka_2.11-0.10.0.1.tgz
apt update && apt install -y openjdk-8-jdk && apt install scala -y
tar xvf kafka_2.11-0.10.0.1.tgz
cp -r kafka_2.11-0.10.0.1/ /usr/local/bin/kafka/
```
## docker-compose
```
curl -L https://github.com/docker/compose/releases/download/1.7.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose && chmod +x /usr/local/bin/docker-compose
```

## elasticsearch
```
wget https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/deb/elasticsearch/2.3.1/elasticsearch-2.3.1.deb
dpkg -i elasticsearch-2.3.1.deb
service elasticsearch start
```
cluster:
```
ls /etc/elasticsearch
vim elasticsearch.yml
```
edit
```
custer.name: yd
node.name: n1
```
[full requirement](https://github.com/rengokantai/psadelasticsearclu/edit/master/README.md)
## jdk,jre
if repo exists(u16)
```
apt-get install openjdk-8-jdk -y
apt-get install openjdk-8-jre -y
```
else
```
add-apt-repository ppa:webupd8team/java -y
apt-get update
apt-get install oracle-java8-installer -y
```


## golang 1.7 
### u16
```
curl -O https://storage.googleapis.com/golang/go1.7.1.linux-amd64.tar.gz
tar xvf go1.7.1.linux-amd64.tar.gz
sudo chown -R root:root ./go && sudo mv go /usr/local 
```
edit env and path
```
sudo vim ~/.profile
```
edit
```
export GOPATH=$HOME/pjroot
export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
```
refresh source
```
source ~/.profile
```
crate files:
```
mkdir -p work/src/github.com/rengokantai/hello
vim work/src/github.com/rengokantai/hello/hello.go
go install github.com/rengokantai/hello
```
then run
```
hello
```

## Jenkins2
### MAC
```
java -jar jenkins.war  
```
### CentOS
repo: https://pkg.jenkins.io/redhat/
```
yum -y install java
wget https://pkg.jenkins.io/redhat/jenkins-2.54-1.1.noarch.rpm
rpm -Uvh j
systemctl enable jenkins && system start jenkins
vi /var/lib/jenkins/secrets/initialAdminPassword
```
copy and paste localhost:8080


## mysql
### CentOS
```
wget https://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm
rpm -ivh mysql57-community-release-el7-9.noarch.rpm
yum install mysql-server
systemctl start mysqld
grep 'temporary password' /var/log/mysqld.log
mysql_secure_installation
```






## percona
```
wget https://repo.percona.com/apt/percona-release_0.1-4.$(lsb_release -sc)_all.deb
dpkg -i percona-release_0.1-4.$(lsb_release -sc)_all.deb 
sudo apt-get update && sudo apt-get install percona-server-server-5.7
sudo apt-get install percona-xtradb-cluster-57
//sudo apt-get install percona-xtradb-full-57
```

## postgis
```
wget http://download.osgeo.org/postgis/source/postgis-2.3.0.tar.gz
tar xvzf postgis-2.3.0.tar.gz 
cd postgis-2.3.0 
./configure 
make && make install
```

## teamcity
```
wget https://download.jetbrains.com/teamcity/TeamCity-2017.1.tar.gz
Teamcity/bin/runAll.sh start
```
