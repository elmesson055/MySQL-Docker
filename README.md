# MySQL Docker Container Setup

This repository contains Docker configuration for running a MySQL database server with data persistence.

## Prerequisites

- Docker Desktop installed
- Docker Compose installed

## Configuration

The project uses the following environment variables (defined in `.env`):

- `MYSQL_CONTAINER_NAME`: Container name (default: MYSql_learning)
- `MYSQL_PASSWORD`: Root password for MySQL
- `MYSQL_PORT`: Port mapping (default: 3306)
- `MYSQL_DATA_PATH`: Directory for MySQL data persistence
- `MYSQL_BACKUP_PATH`: Directory for database backups

## Getting Started

1. Clone this repository:
```bash
git clone <repository-url>
```
2. Create required directories:
```bash
mkdir data Backup
 ```

3. Start the container:
```bash
docker-compose up -d
 ```

4. Verify the container is running:
```bash
docker ps
 ```

## Connecting to MySQL
- Host : localhost
- Port : 3306 (or the port specified in .env)
- Username : root
- Password : MYSql@123 (or the password specified in .env)
### Using MySQL CLI
```bash
docker exec -it MYSql_learning mysql -uroot -p
 ```
```

## Data Persistence
- Database files are stored in the ./data directory
- Backups can be stored in the ./Backup directory
## Common Commands
Stop the container:

```bash
docker-compose down
 ```

View container logs:

```bash
docker logs MYSql_learning
 ```

Create a database backup:

```bash
docker exec MYSql_learning mysqldump -uroot -p[YOUR_PASSWORD] [DATABASE_NAME] > ./Backup/backup.sql
 ```
```

Restore a database:

```bash
docker exec -i MYSql_learning mysql -uroot -p[YOUR_PASSWORD] [DATABASE_NAME] < ./Backup/backup.sql
 ```
```

## Troubleshooting
1. If the container fails to start, check:
   
   - Docker Desktop is running
   - No other service is using port 3306
   - Environment variables are properly set
2. If you can't connect to MySQL:
   
   - Verify the container is running
   - Check the port mapping
   - Ensure you're using the correct password
## Security Note
Remember to:

- Change the default root password
- Never expose the MySQL port in production without proper security measures
- Regularly backup your database