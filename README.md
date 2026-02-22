# Static Website Deployment on EC2 (Nginx web server)

## 1. Launch EC2 (Ubuntu)

## 2. Install Nginx
```bash
sudo apt update
sudo apt install nginx -y
systemctl start nginx
systemctl enable nginx
systemctl status nginx
```
---

## 3. Clone Repository
```bash
cd /var/www/html
git clone https://github.com/shwetabhore18/staticwebsite-templates.git
```
---

## 4. Move Website Files
```bash
sudo rm defualt .html file
sudo mv -r staticwebsite-templates/coffee/* /var/www/html/
```

## 5. Restart Nginx
```bash
sudo systemctl restart nginx
copy public ip and check on browser
```

---

## NOTE:
```bash
    ubuntu default root for nginx is /var/ww/html
    also nginx has /usr/share/nginx/html but ubuntu does not use this depending on the 
    installation "ubuntu (apt install nginx) uses /var/www/html<br>
```
---

``` bash
    if we want we can change the location to server nginx from /usr/share/nginx/html
    edit vim /etc/nginx/sites-available/default  change -> root /usr/share/nginx/html;
    it will change the root location for nginx <br>
```