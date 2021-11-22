1.安装java运行环境
yum install java-1.8.0-openjdk* -y

2.下载jenkins安装包 
jenkins-2.284-1.1.noarch.rpm

3.安装
rpm -ivh jenkins-2.284-1.1.noarch.rpm

4.修改jenkin配置
JENKINS_USER="root"
JENKINS_PORT="8088"

5.启动jenkins
systemctl start jenkins

6.