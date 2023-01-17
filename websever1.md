## documentation for the webserver

`sudo yum install nfs-utils nfs4-acl-tools -y`
`sudo mkdir /var/www`
`sudo mount -t nfs -o rw,nosuid 172.31.85.49:/mnt/apps /var/www`
`df -h`
![nsf mounted](./images/nsf%20mounted.png)
`sudo touch /var/www/test.md`
`sudo vi /etc/fstab`
`sudo yum install httpd -y`
`sudo dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm`

`sudo dnf install dnf-utils http://rpms.remirepo.net/enterprise/remi-release-8.rpm`
`sudo dnf module reset php`
`sudo dnf module enable php:remi-7.4`
`sudo dnf install php php-opcache php-gd php-curl php-mysqlnd`
`sudo systemctl start php-fpm`
`sudo systemctl enable php-fpm`
`sudo setsebool -P httpd_execmem 1`
`sudo vi /etc/fstab`
![connection to the nfs](./images/cfh%20connection.png)
`sudo yum install git`
`git clone https://github.com/darey-io/tooling.git`
`sudo cp -R html/. /var/www/html`
`sudo setenforce 0`
`sudo vi /var/www/html/functions.php`
`sudo yum install mysql -y`
`mysql -h 172.31.84.152 -u webaccess -p tooling < tooling-db.sql`

