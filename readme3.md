
# Installing ThingsBoard on Windows

## 🔗 Links
[Thingsbord Contribution Guide](https://thingsboard.io/docs/user-guide/contribution/how-to-contribute/#:~:text=We%20are%20constantly%20looking%20for,(or%20something%20very%20similar).)


## Run Locally

Clone the project

```bash
  git clone https://github.com/thingsboard/thingsboard.git
```

Go to the project directory

```bash
 cd D:\thingsboard
```

Install dependencies

```bash
npm install -g cross-env 

npm install -g npm@10.5.0

npm install -g webpack 

```
## Screenshots

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/1.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/2.png)

Before importing the project into the IDE please build it using Maven tool from the root folder:

Step 2. ThingsBoard service installation
```bash
https://github.com/thingsboard/thingsboard/releases/download/v3.6.3/thingsboard-windows-3.6.3.zip
```

Step 3. Configure ThingsBoard database

Create ThingsBoard Database

## Screenshots

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/6.png)

Step 2. ThingsBoard service installation
```bash
C:\Program Files (x86)\thingsboard\conf\thingsboard.yml
```
Step 2. ThingsBoard service installation
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

C:\Program Files (x86)\thingsboard>install.bat --loadDemo
Detecting Java version installed.
CurrentVersion 110
Java 11 found!
Installing thingsboard ...
...
ThingsBoard installed successfully!


## Screenshots

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/6.png)

[Optional] NoSQL Database for timeseries data: Cassandra
[Not Configured]

Running development environment

Running UI container in hot redeploy mode.

Step 7. Start ThingsBoard service
Now let’s start the ThingsBoard service! Open the command prompt as an Administrator and execute the following command:

net start thingsboard

Expected output:

The ThingsBoard Server Application service is starting.
The ThingsBoard Server Application service was started successfully.

In order to restart the ThingsBoard service you can execute following commands:

net stop thingsboard
net start thingsboard


Go to the project directory

```bash
 cd D:\thingsboard\ui-ngx
mvn clean install -P yarn-start
```
## Screenshots

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/7.png)

Running server-side container

## Screenshots

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/8.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/9.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/10.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/11.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/12.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/13.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/14.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/15.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/16.png)

![App Screenshot](https://github.com/sushanth91/thingsboarderror/blob/main/17.png)



## 🔗 Installing ThingsBoard on Windows
[Error Logs](https://thingsboard.io/docs/user-guide/install/windows/)






