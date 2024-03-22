
## Screenshots

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/IOTlogin1.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/IOTsysadmin.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/IOTtenant.png)

# Installing ThingsBoard on Windows

## 🔗 Links
[Thingsbord Contribution Guide](https://thingsboard.io/docs/user-guide/install/windows/?windowsThingsboardQueue=inmemory).)

Step 1. Install Java 11 (OpenJDK)

```bash
java -version
```

Step 2. ThingsBoard service installation
Download and extract the package.

```bash
https://github.com/thingsboard/thingsboard/releases/download/v3.6.3/thingsboard-windows-3.6.3.zip
```

Step 3. Configure ThingsBoard database

Create ThingsBoard Database

## Screenshots

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/6.png)

```bash
C:\Program Files (x86)\thingsboard\conf\thingsboard.yml
```

```bash
# SQL DAO Configuration
spring:
  data:
    jpa:
      repositories:
        enabled: "true"
  jpa:
    open-in-view: "false"
    hibernate:
      ddl-auto: "none"
  datasource:
    driverClassName: "${SPRING_DRIVER_CLASS_NAME:org.postgresql.Driver}"
    url: "${SPRING_DATASOURCE_URL:jdbc:postgresql://localhost:5432/thingsboard}"
    username: "${SPRING_DATASOURCE_USERNAME:postgres}"
    password: "${SPRING_DATASOURCE_PASSWORD:postgres}"
    hikari:
      maximumPoolSize: "${SPRING_DATASOURCE_MAXIMUM_POOL_SIZE:5}"
```

```bash
  sql:
      postgres:
        # Specify partitioning size for timestamp key-value storage. Example: DAYS, MONTHS, YEARS, INDEFINITE.
        ts_key_value_partitioning: "${SQL_POSTGRES_TS_KV_PARTITIONING:MONTHS}"
```

Step 4. Choose ThingsBoard queue service
In Memory
(built-in and default)

Step 5. [Optional] Memory update for slow machines (1GB of RAM)

C:\Program Files (x86)\thingsboard\thingsboard.xml

Locate the following lines to the configuration file.

<startargument>-Xms512m</startargument>
<startargument>-Xmx1024m</startargument>

and change them to

<startargument>-Xms256m</startargument>
<startargument>-Xmx256m</startargument>

Step 6. Run installation script
Launch windows shell (Command Prompt) as Administrator. Change directory to your ThingsBoard installation directory.

Execute install.bat script to install ThingsBoard as a Windows service (or run “install.bat –loadDemo” to install and add demo data). This means it will be automatically started on system startup. Similar, uninstall.bat will remove ThingsBoard from Windows services. The output should be similar to this one:

```bash
C:\Program Files (x86)\thingsboard>install.bat --loadDemo
Detecting Java version installed.
CurrentVersion 110
Java 11 found!
Installing thingsboard ...
...
ThingsBoard installed successfully!
```

Step 7. Start ThingsBoard service

Now let’s start the ThingsBoard service! Open the command prompt as an Administrator and execute the following command:

```bash
net start thingsboard
```

Expected output:

```bash
The ThingsBoard Server Application service is starting.
The ThingsBoard Server Application service was started successfully.
```

In order to restart the ThingsBoard service you can execute following commands:

```bash
net stop thingsboard
net start thingsboard
```



