
# scanPBNJ

scanPBNJ is a network scanning tool similar to nmap but with additional features, including the ability to save information directly into a MySQL database.

```bash
# Start by starting the MySQL service
sudo systemctl start mysql

# Connect to MySQL as root
mysql -u root -p

# Create a new database for scanPBNJ
CREATE DATABASE BTpbnj;
EXIT; # Exit MySQL

# Create a user for scanPBNJ
mysql -u root -p
CREATE USER 'tester'@'localhost' IDENTIFIED BY 'password';
GRANT ALL ON Btpbnj.* TO 'tester'@'localhost';
EXIT; # Exit MySQL again

# Create a directory for scanPBNJ configuration files
mkdir -p ./pbnj-2.0

# Copy the default MySQL configuration file
cp /usr/share/doc/pbnj/examples/mysql.yaml config.yaml

# Edit the configuration file
nano config.yaml

# In the configuration file, set up the database connection details:
db:
  driver: mysql
  database: BTpbnj
  user: tester
  passwd: password
  host: localhost
  port: 3306
```

Now you can start using scanPBNJ:

```bash
# Run a scan against a specific IP address
/usr/local/bin/scanpbnj -a "-p- -T4" 192.168.1.1

# After running the scan, connect to MySQL to view the results
mysql -u tester -p BTpbnj

# Once connected, you can view tables and data:
SHOW TABLES;
DESCRIBE machines; # To see information about the 'machines' table
SELECT * FROM machines; # To view all data in the 'machines' table
```

### Explanation of scanPBNJ Usage

1. **Installation**: ScanPBNJ is installed at `/usr/local/bin/scanpbnj`. You can run it using the command `scanpbnj`.

2. **Configuration**: The MySQL configuration is stored in `config.yaml`. Make sure to set up the correct database name, user, password, host, and port.

3. **Running Scans**: The basic syntax for running a scan is:

   ```
   /usr/local/bin/scanpbnj [options] <target>
   ```

   In your example, `-a "-p- -T4"` sets aggressive options (-a) including port scanning (-p-) and using 4 threads (-T4).

4. **Data Storage**: ScanPBNJ stores its results directly in the specified MySQL database. After running a scan, you can connect to the database to view the collected information.

5. **Database Structure**: Typically, scanPBNJ creates tables like 'machines' and 'services' to store scan results.

6. **Querying Results**: Once connected to the MySQL database, you can use SQL queries to analyze the scan results, such as viewing all machines discovered (`SELECT * FROM machines;`) or details about specific services (`DESCRIBE services;`).

Remember to replace placeholder IP addresses (like 192.168.1.1) with actual target IP addresses when performing scans. Always ensure you have permission to scan the targets before running network scans.

Citations:
[1] <https://hevodata.com/learn/flask-mysql/>
[2] <https://docs.newrelic.com/install/mysql/>
[3] <https://www.elastic.co/guide/en/integrations/current/mysql.html>
[4] <https://www.baeldung.com/java-connect-mysql>
[5] <https://www.digitalocean.com/community/tutorials/spring-mvc-hibernate-mysql-integration-crud-example-tutorial>
[6] <https://signoz.io/blog/opentelemetry-mysql-metrics-monitoring/>
[7] <https://www.youtube.com/watch?v=_E2-cVna-3M>
[8] <https://learn.microsoft.com/en-us/azure/mysql/flexible-server/overview>
[9] <https://help.scalegrid.io/docs/connect-mysql-to-powerbi>
[10] <https://planetscale.com/>
