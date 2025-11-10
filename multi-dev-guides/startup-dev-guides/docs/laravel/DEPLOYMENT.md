# Laravel Deployment Guidelines

## Table of contents
- Overview
- Pre-deployment checklist
- Deployment environments
- Deployment steps
- Post-deployment
- Rollback plan

## Overview
This document provides comprehensive guidelines for deploying Laravel applications. It covers the necessary steps, platform-specific considerations, and recommended tools to ensure a smooth deployment process.

## Pre-Deployment Checklist
Before deploying your Laravel application, ensure the following:

- [ ] Code is reviewed and merged into the main branch.
- [ ] All tests (unit, integration, and end-to-end) have passed.
- [ ] Environment variables are configured correctly.
- [ ] The database is migrated and seeded if necessary.
- [ ] Caching mechanisms are set up (config, route, view).

## Deployment Environments
Laravel applications can be deployed to various environments. The most common include:

1. **Shared Hosting**
   - Ensure the hosting provider supports PHP and Composer.
   - Upload files via FTP/SFTP.
   - Set the document root to the `public` directory.

2. **Virtual Private Server (VPS)**
   - Use a VPS provider (e.g., DigitalOcean, Linode).
   - Install necessary software (PHP, Composer, Nginx/Apache, MySQL).
   - Configure Nginx/Apache to serve the application from the `public` directory.

3. **Cloud Platforms**
   - **AWS Elastic Beanstalk**: Use the Laravel deployment package for easy deployment.
   - **Heroku**: Use the Heroku CLI and configure the `Procfile` for Laravel.
   - **Docker**: Create a Dockerfile and use Docker Compose for multi-container setups.

## Deployment Steps

### 1. Prepare the Server
- Update the server packages:
  ```
  sudo apt update && sudo apt upgrade
  ```
- Install PHP and required extensions:
  ```
  sudo apt install php php-cli php-fpm php-mysql php-xml php-mbstring php-zip
  ```

### 2. Clone the Repository
- Navigate to the web root directory:
  ```
  cd /var/www/html
  ```
- Clone the repository:
  ```
  git clone <repository-url> your-app-name
  ```

### 3. Install Dependencies
- Navigate to the application directory:
  ```
  cd your-app-name
  ```
- Install Composer dependencies:
  ```
  composer install --optimize-autoloader --no-dev
  ```

### 4. Configure Environment
- Copy the `.env.example` to `.env`:
  ```
  cp .env.example .env
  ```
- Update the `.env` file with the production database and application settings.

### 5. Generate Application Key
- Run the following command to generate the application key:
  ```
  php artisan key:generate
  ```

### 6. Run Migrations
- Execute database migrations:
  ```
  php artisan migrate --force
  ```

### 7. Set Permissions
- Set the correct permissions for storage and bootstrap/cache directories:
  ```
  sudo chown -R www-data:www-data storage bootstrap/cache
  sudo chmod -R 775 storage bootstrap/cache
  ```

### 8. Configure Web Server
- For **Nginx**, create a server block:
  ```
  server {
      listen 80;
      server_name your-domain.com;
      root /var/www/html/your-app-name/public;

      index index.php index.html index.htm;

      location / {
          try_files $uri $uri/ /index.php?$query_string;
      }

      location ~ \.php$ {
          include snippets/fastcgi-php.conf;
          fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
          fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
          include fastcgi_params;
      }
  }
  ```

### 9. Restart Web Server
- Restart Nginx or Apache to apply changes:
  ```
  sudo systemctl restart nginx
  ```

## Post-Deployment
- Verify the application is running by accessing the URL.
- Check logs for any errors:
  ```
  tail -f storage/logs/laravel.log
  ```

## Rollback Plan
In case of deployment failure, follow these steps to rollback:
1. Restore the previous version from the backup.
2. Revert database changes if necessary.
3. Clear cache:
   ```
   php artisan cache:clear
   ```

## Conclusion
Following these guidelines will help ensure a successful deployment of your Laravel application. Always test thoroughly in a staging environment before deploying to production.