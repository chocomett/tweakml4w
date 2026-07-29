# 🐘 03. PHP Development

This guide installs PHP and the tools required for PHP web development.

**⏱️ Estimated Time:** 15–20 minutes

---

## Step 1. Install PHP

Install PHP and the most commonly used extensions.

```bash
sudo pacman -S \
php \
php-apache \
php-pgsql \
php-gd \
php-intl \
php-sqlite \
php-zip \
php-curl \
php-mbstring \
php-xml
```

---

## Step 2. Install Composer

Install Composer.

```bash
sudo pacman -S composer
```

---

## Step 3. Install Apache

Install Apache HTTP Server.

```bash
sudo pacman -S apache
```

Enable Apache.

```bash
sudo systemctl enable httpd
sudo systemctl start httpd
```

---

## Step 4. Configure PHP

Open the PHP configuration file.

```bash
sudo nano /etc/php/php.ini
```

Enable the following extensions.

```ini
extension=curl
extension=gd
extension=intl
extension=mbstring
extension=pdo_pgsql
extension=pgsql
extension=sqlite3
extension=zip
```

Save the file.

Restart Apache.

```bash
sudo systemctl restart httpd
```

---

## Step 5. Verify Installation

Check the installed versions.

```bash
php -v
composer --version
apachectl -v
```

---

## Notes

> 💡 I use PostgreSQL as my primary database.

> 💡 Composer is used to manage PHP dependencies.

> 💡 This setup works for Laravel and CodeIgniter.

---

## Useful Commands

### PHP

| Purpose | Command |
| ------- | ------- |
| PHP version | `php -v` |
| Show loaded modules | `php -m` |
| PHP configuration | `php --ini` |
| PHP information | `php -i` |

Example:

```bash
php -v
php -m
```

---

### Composer

| Purpose | Command |
| ------- | ------- |
| Composer version | `composer --version` |
| Install dependencies | `composer install` |
| Update dependencies | `composer update` |
| Create a project | `composer create-project` |
| Install a package | `composer require package_name` |
| Remove a package | `composer remove package_name` |

Example:

```bash
composer install

composer require laravel/sanctum
```

---

### Apache

| Purpose | Command |
| ------- | ------- |
| Start Apache | `sudo systemctl start httpd` |
| Stop Apache | `sudo systemctl stop httpd` |
| Restart Apache | `sudo systemctl restart httpd` |
| Enable Apache | `sudo systemctl enable httpd` |
| Disable Apache | `sudo systemctl disable httpd` |
| Check Apache status | `systemctl status httpd` |

---

### Laravel

| Purpose | Command |
| ------- | ------- |
| Create project | `composer create-project laravel/laravel app` |
| Start development server | `php artisan serve` |
| Run migrations | `php artisan migrate` |
| Generate application key | `php artisan key:generate` |

Example:

```bash
composer create-project laravel/laravel portfolio

cd portfolio

php artisan serve
```

---

### CodeIgniter

| Purpose | Command |
| ------- | ------- |
| Create project | `composer create-project codeigniter4/appstarter app` |
| Start development server | `php spark serve` |

Example:

```bash
composer create-project codeigniter4/appstarter portfolio

cd portfolio

php spark serve
```

---

## Troubleshooting

### ❌ composer: command not found

Verify Composer is installed.

```bash
composer --version
```

---

### ❌ PHP extensions are missing

Open:

```bash
sudo nano /etc/php/php.ini
```

Enable the required extensions.

Restart Apache.

```bash
sudo systemctl restart httpd
```

---

### ❌ Apache service failed

Check the service status.

```bash
systemctl status httpd
```

---

## Next

➡️ **04-docker.md**