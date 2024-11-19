# WordPress Docker Setup with FPM and MySQL

This repository provides a simple setup for deploying WordPress on a VPS using Docker Compose, PHP-FPM, MySQL, and NGINX. It includes configurations for setting up a secure, high-performance WordPress environment with SSL enabled using Certbot.

---

## 📋 Prerequisites

1.  **Docker & Docker Compose**: Ensure Docker and Docker Compose are installed on your VPS.
2. **Configure NGINX and SSL Certificates:** Follow the [Nginx Configuration Steps](./nginx-config) to set up Nginx for your WordPress installation.

## 🚀 Setup Instructions

1. **Clone the repository**
   ```sh
   git clone https://github.com/alvarovalverde03/wordpress-docker-nginx.git
   cd wordpress-docker-nginx
   ```

   > **ℹ️ Note:** It's recommended to change the folder name to customize the container prefix. For example:
   > ```sh
   > mv wordpress-docker-nginx my-wordpress-setup
   > cd my-wordpress
   > ```

2. **Setup environment variables:** Edit the `.env` file to configure database credentials and WordPress settings.
    
   > **ℹ️ Note:** Make sure to replace all instances of `your-domain` in the `docker-compose.yml` file with your actual domain or any name you prefer.
   
3. **Launch Docker services:** Run the following command to start the containers.
   ```sh
   docker-compose up -d
   ```

4. **Setup WordPress:** Open your browser and navigate to your domain. Follow the WordPress setup wizard to complete the installation.

---

## 🔗 Useful Links

- [NGINX Configuration Steps](./nginx-config)
- [Docker Compose Documentation](https://docs.docker.com/compose/)
- [WordPress Documentation](https://wordpress.org/documentation/)
- [Docker Hub - WordPress](https://hub.docker.com/_/wordpress/)
- [Docker Hub - MySQL](https://hub.docker.com/_/mysql/)
