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

Ubuntu default root for **Nginx** is `/var/www/html`.

Although Nginx also has `/usr/share/nginx/html`,  
**but Ubuntu (apt install nginx)** uses `/var/www/html`.
depending on the installation for apt install nginx is `/var/www/html`.

If you want to **change the root location**, edit:

```bash
sudo vim /etc/nginx/sites-available/default
```

Then change:

```bash
root /usr/share/nginx/html;
```