# NGINX Configuration for WordPress

This folder contains the necessary Nginx configuration files to integrate with the Dockerized WordPress setup. Follow the steps below to configure Nginx and enable SSL on your VPS.

Make sure to replace all instances of `your-domain` with your actual domain name.

---

## 🚀 Steps to Configure Nginx

1. **Install NGINX:** If NGINX is not installed on your VPS, install it using the following command:

   ```sh
   sudo apt update
   sudo apt install nginx
   ```

2. **Configure NGINX:** Move the `domain.conf` file to NGINX's `sites-available` directory:
   
    ```sh
    sudo cp domain.conf /etc/nginx/sites-available/your-domain
    ```

3. **Enable the Site:** Create a symbolic link to enable the site configuration:

    ```sh
    sudo ln -s /etc/nginx/sites-available/your-domain /etc/nginx/sites-enabled/
    ```

    > **ℹ️ Note:** Delete `default` file from `sites-enabled` directory if it exists to avoid conflicts.
    > 
    > If you have multiple domains, repeat steps 2 and 3 for each domain.

4. **Test Configuration:** Verify that the configuration is valid:

    ```sh
    sudo nginx -t
    ```

5. **Restart NGINX:** Apply the changes by restarting Nginx:

    ```sh
    sudo systemctl restart nginx
    ```

6. **Set up SSL (optional but recommended):** Use Certbot to generate SSL certificates:

    ```sh
    sudo apt install certbot python3-certbot-nginx

    sudo certbot --nginx -d your-domain.com -d www.your-domain.com
    ```

    > **ℹ️ Note:** Ensure DNS records for your domain point to server IP address.


## 🔗 Useful Links

- [NGINX Reverse Proxy](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/)
- [Certbot Documentation](https://certbot.eff.org/docs/)