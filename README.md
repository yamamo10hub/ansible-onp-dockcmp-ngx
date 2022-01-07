# nginx in docker-compose setup
onpreにセットアップしたCentos7xにdocker-composeとnginxを設定する  
ansibleのplaybook  
  
## host
対象がCentOS7.xとし、以下設定がされている想定  
* admin追加 sudo登録
* selinux disabled
* firewalld disable
* network
  
## 実行

```
git clone this
cd hcitest-docker
vi group_vars/all # dockercomposeのversionを調べて書き換える
vi ssh_config   # change targetIP
ansible-playbook site.yml --syntax-check
ansible-playbook site.yml --check
ansible-playbook site.yml

# activate nginx on target host:80
curl -vk http://[host ip]/
```
