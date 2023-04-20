# aws_wordpress

#Elastic IP with domain - https://medium.com/@lyle-okoth/how-to-create-an-elastic-ip-address-on-aws-and-point-your-domain-to-it-61d45058667a

#LAMP server for AMI Linux 2 - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-lamp-amazon-linux-2.html
mariaDB PW: v...

#enable SSL/TLS: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/SSL-on-amazon-linux-2.html

#Certbot: https://certbot.eff.org/instructions?ws=apache&os=centosrhel8
	sudo amazon-linux-extras install epel
	sudo yum install certbot-apache

	#https://stackoverflow.com/questions/59549309/unable-to-find-a-virtual-host-listening-on-port-80-please-add-a-virtual-host

	cd /etc/httpd/conf.d
	sudo nano yourDomainName.conf
	Paste, edit, and save the following:

	<VirtualHost *:80>
		ServerName yourDomainName.com
		DocumentRoot /var/www/html
		ServerAlias www.yourDomainName.com
		ErrorLog /var/www/error.log
		CustomLog /var/www/requests.log combined
	</VirtualHost>

#Host wordpress: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/hosting-wordpress.html
