mysql -uroot -p

2.SET PASSWORD FOR'root'@'localhost'= PASSWORD('ruiyun2020.');

3.GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'root' WITH GRANT OPTION;

4.flush privileges;

5.grant all privileges on *.* to 'root'@'%' identified by 'ruiyun2020.';

