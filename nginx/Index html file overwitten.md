# Fix: Nginx Reverted to Default Index Page

## Problem

After a system update or reinstall, Nginx may start serving the default welcome page instead of your custom `index.html`. This typically happens because your files were placed in `/usr/share/nginx/html`, which can be overwritten by updates.

---

## Fix Instructions

Move your site to a safer location and update the Nginx config:

# 1. Create a safer directory for your site
`sudo mkdir -p /var/www/vst`

# 2. Copy your existing site files
`sudo cp -r /usr/share/nginx/html/* /var/www/vst/`

# 3. Fix permissions
`sudo chown -R www-data:www-data /var/www/vst`

`sudo chmod -R 755 /var/www/vst`

# 5. Edit Nginx’s main config
`sudo nano /etc/nginx/nginx.conf`

Replace or add inside the `http {}` block:
```
server {
    listen 80;
    server_name 192.168.1.43;

    root /var/www/vst;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

# 6. Reload Nginx
`sudo nginx -t`

`sudo systemctl reload nginx`



