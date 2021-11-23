1.安装java运行环境
yum install java-1.8.0-openjdk* -y

2.下载jenkins安装包 
jenkins-2.284-1.1.noarch.rpm

3.安装
rpm -ivh jenkins-2.284-1.1.noarch.rpm

4.修改jenkin配置

vim /etc/sysconfig/jenkins

JENKINS_USER="root"
JENKINS_PORT="8088"

4.1.修改default.json文件

cd /var/lib/jenkins/updates

sed -i 's/http:\/\/updates.jenkins-
ci.org\/download/https:\/\/mirrors.tuna.tsinghua.edu.cn\/jenkins/g' default.json && sed -i
's/http:\/\/www.google.com/https:\/\/www.baidu.com/g' default.json

5.启动jenkins
systemctl start jenkins

- 5.1

  如果出现安装过程中jenkins离线, 

  修改/var/lib/jenkins/updates/default.json  将 http://ww.google.com 修改成 http://www.baidu.com

  修改 /var/lib/jenkins/hudson.model.UpdateCenter.xml  下载插件的源地址 

  改地址默认jenkins默认为：https://updates.jenkins.io/update-center.json，就是因为https的问题，此处我们将其改为http即可，之后重启jenkins服务即可。

  其他国内备用地址（也可以选择使用）：

  https://mirrors.tuna.tsinghua.edu.cn/jenkins/updates/update-center.json

  http://mirror.esuni.jp/jenkins/updates/update-center.json

  重启:systemctl restart jenkins

6.下载插件

​	6.1 下载汉化插件 [Localization: Chinese (Simplified)](https://plugins.jenkins.io/localization-zh-cn) 

​	6.2 下载ssh凭证插件 和 ssh   [SSH Credentials Plugin](https://plugins.jenkins.io/ssh-credentials) 

​    6.3 下载 git插件  git

​    6.4 下载 publish over ssh 用于远程发送到别的服务器 

​	6.5 下载pipleline插件 用于构造流水线

   	