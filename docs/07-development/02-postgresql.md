# 🐘 02. PostgreSQL

This guide installs and configures PostgreSQL for local development.

**⏱️ Estimated Time:** 10–15 minutes

---

## Step 1. Install PostgreSQL

Install PostgreSQL from the official repositories.

```bash
sudo pacman -S postgresql
```

---

## Step 2. Initialize the Database

Initialize the PostgreSQL data directory.

```bash
sudo -iu postgres initdb -D /var/lib/postgres/data
```

> 💡 This only needs to be done once after installing PostgreSQL.

---

## Step 3. Enable PostgreSQL

Enable PostgreSQL to start automatically.

```bash
sudo systemctl enable postgresql
```

Start the service.

```bash
sudo systemctl start postgresql
```

---

## Step 4. Create a PostgreSQL User

Switch to the PostgreSQL user.

```bash
sudo -iu postgres
```

Create a new PostgreSQL user.

```bash
createuser --interactive
```

Example:

```text
Enter name of role to add: john
Shall the new role be a superuser? (y/n) y
```

Exit the PostgreSQL user.

```bash
exit
```

---

## Step 5. Create a Database

Create a new database.

```bash
createdb portfolio
```

---

## Step 6. Connect to PostgreSQL

Connect to the database.

```bash
psql portfolio
```

Exit PostgreSQL.

```sql
\q
```

---

## Verify

Verify the installation.

```bash
psql --version
```

Check the PostgreSQL service.

```bash
systemctl status postgresql
```

List all databases.

```bash
psql -l
```

---

## Notes

> 💡 PostgreSQL stores all database files in `/var/lib/postgres/data`.

> 💡 I use PostgreSQL as my primary database for local web development.

> 💡 All database management is performed using the `psql` command-line interface.

---

## Useful Commands

### Service Management

| Purpose | Command |
| ------- | ------- |
| Start PostgreSQL | `sudo systemctl start postgresql` |
| Stop PostgreSQL | `sudo systemctl stop postgresql` |
| Restart PostgreSQL | `sudo systemctl restart postgresql` |
| Check service status | `systemctl status postgresql` |
| Enable on boot | `sudo systemctl enable postgresql` |
| Disable on boot | `sudo systemctl disable postgresql` |

Example:

```bash
sudo systemctl start postgresql
systemctl status postgresql
```

---

### Database Management

| Purpose | Command |
| ------- | ------- |
| List all databases | `psql -l` |
| Create a database | `createdb database_name` |
| Delete a database | `dropdb database_name` |
| Connect to a database | `psql database_name` |

Example:

```bash
createdb portfolio
psql portfolio
dropdb portfolio
```

---

### User Management

| Purpose | Command |
| ------- | ------- |
| Create a user | `createuser --interactive` |
| Delete a user | `dropuser username` |
| List all users | `\du` |

Example:

```bash
createuser --interactive
dropuser john
```

---

### psql Commands

| Purpose | Command |
| ------- | ------- |
| List databases | `\l` |
| Connect to database | `\c database_name` |
| List tables | `\dt` |
| Describe table | `\d table_name` |
| List schemas | `\dn` |
| List users | `\du` |
| Show current database | `SELECT current_database();` |
| Show current user | `SELECT current_user;` |
| Exit psql | `\q` |

Example:

```sql
\l
\c portfolio
\dt
\d users
\du

SELECT current_database();
SELECT current_user;

\q
```

---

### Backup & Restore

| Purpose | Command |
| ------- | ------- |
| Backup a database | `pg_dump database_name > backup.sql` |
| Restore a database | `psql database_name < backup.sql` |

Example:

```bash
pg_dump portfolio > backup.sql
psql portfolio < backup.sql
```

---

## Troubleshooting

### ❌ PostgreSQL service is not running

Start the service.

```bash
sudo systemctl start postgresql
```

---

### ❌ Database is not initialized

Initialize the database.

```bash
sudo -iu postgres initdb -D /var/lib/postgres/data
```

---

### ❌ Cannot connect to PostgreSQL

Verify that the PostgreSQL service is running.

```bash
systemctl status postgresql
```

List available databases.

```bash
psql -l
```

---

## Next

➡️ **03-php.md**