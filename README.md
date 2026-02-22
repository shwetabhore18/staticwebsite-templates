# Static Website Deployment on EC2 (Nginx web server)

## 1. Launch EC2 (Ubuntu)

## 2. Install Nginx
sudo apt update<br>
sudo apt install nginx -y<br>
systemctl start nginx<br>
systemctl enable nginx<br>
systemctl status nginx

## 3. Clone Repository
cd /var/www/html
git clone https://github.com/shwetabhore18/staticwebsite-templates.git

## 4. Move Website Files
sudo rm defualt .html file
sudo mv -r staticwebsite-templates/coffee/* /var/www/html/

## 5. Restart Nginx
sudo systemctl restart nginx
copy public ip and check on browser