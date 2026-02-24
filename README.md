# Static Website Deployment on EC2 (Nginx web server)


# Deployment on Ubuntu (Nginx)

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

## Website Output Screenshot

<img src="images/coffee_output.png" width="600">


---

# Deployment on Amazon Linux (Nginx)

## 1. Launch EC2 (Amazon Linux)

## 1. Install Nginx

### Amazon Linux 

```bash
sudo yum update -y
sudo yum install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
sudo systemctl status nginx
```

## 2. Default Nginx Root Directory

On Amazon Linux, the default root directory is:

`/usr/share/nginx/html`

---

## 3. Deploy Website

```bash
cd ~
git clone https://github.com/shwetabhore18/staticwebsite-templates.git
```

Remove default Nginx files:

```bash
sudo rm -rf /usr/share/nginx/html/*
```

Copy website files (example: coffee template):

```bash
you have to present in the root directory
sudo cp -r /staticwebsite-templates/yoga/* /usr/share/nginx/html/
sudo systemctl restart nginx
OR 
cd /usr/share/nginx/html/
cp -r ~/staticwebsite-templates/yoga/* .
```

## Website Output Screenshot

<img src="images/yoga_output.png" width="600">

Now open your EC2 Public IP in browser.