# Static Website Deployment on EC2 (Nginx web server)

## 1. Launch EC2 (Ubuntu)

## 2. Install Nginx
~ sudo apt update<br>
~ sudo apt install nginx -y<br>
~ systemctl start nginx<br>
~ systemctl enable nginx<br>
~ systemctl status nginx

## 3. Clone Repository
~ cd /var/www/html<br>
~ git clone https://github.com/shwetabhore18/staticwebsite-templates.git

## 4. Move Website Files
~ sudo rm defualt .html file<br>
~ sudo mv -r staticwebsite-templates/coffee/* /var/www/html/

## 5. Restart Nginx
~ sudo systemctl restart nginx<br>
~ copy public ip and check on browser

## NOTE:
``` ubuntu default root for nginx is /var/ww/html<br>
    also nginx has /usr/share/nginx/html but ubuntu does not use this depending on the 
    installation "ubuntu (apt install nginx) uses /var/www/html<br>

``` if we want we can change the location to server nginx from /usr/share/nginx/html<br>
    edit vim /etc/nginx/sites-available/default  change -> root /usr/share/nginx/html;
    it will change the root location for nginx <br>