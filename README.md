#### set
######elasticsearch
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
######jdk,jre
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
