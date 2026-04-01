# Blog Project

> **Note**: This is a draft section. Add a comprehensive description of the project here later.

## Features (Draft)
*   [ ] Feature 1
*   [ ] Feature 2
*   [ ] Feature 3

---

## Local Development

### Prerequisites

*   PHP >= 8.4
*   [Composer](https://getcomposer.org/)
*   [Symfony CLI](https://symfony.com/download)
*   A database server (e.g., PostgreSQL, MySQL, SQLite)

### Setup Instructions

1.  **Clone the repository & navigate to the project directory:**
    ```bash
    git clone <repository-url>
    cd blog
    ```

2.  **Install PHP dependencies:**
    ```bash
    composer install
    ```

3.  **Environment Variables:**
    Review the `.env` file. To override any environment variables for local development (like the `DATABASE_URL`), create a `.env.local` file:
    ```bash
    cp .env .env.local
    ```
    *Update `.env.local` with your local database credentials.*

4.  **Database Setup:**
    Create the database and run the migrations to set up the schema:
    ```bash
    php bin/console doctrine:database:create
    php bin/console doctrine:migrations:migrate
    ```

5.  **Assets & Frontend (AssetMapper / SASS):**
    Install third-party Javascript packages via ImportMap and compile SASS:
    ```bash
    php bin/console importmap:install
    php bin/console sass:build
    ```
    *Tip: During active development, you can open a new terminal tab and watch for SASS changes using:*
    ```bash
    php bin/console sass:build --watch
    ```

6.  **Run the local development server:**
    ```bash
    symfony serve -d
    ```
    The application will typically be accessible at `http://127.0.0.1:8000`.

### Running Tests (Optional)

To run the PHPUnit test suite:
```bash
php bin/phpunit
```

### Code Formatting

This project uses PHP CS Fixer. To format the code according to the project's standards:
```bash
vendor/bin/php-cs-fixer fix
```
