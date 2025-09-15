# Run ```Oracle19c Database``` in ```Mac M1/M2``` using ```Docker```

## Prerequisite
- [Docker](https://www.docker.com/)
- [Git](https://git-scm.com/)
- [Visual Studio Code](https://code.visualstudio.com/)

## Steps to follow

### 1. Download the Oracle Database 19c for LINUX ARM (aarch64) file
Go to the page -> [Database Software Downloads | Oracle India](https://www.oracle.com/in/database/technologies/oracle-database-software-downloads.html) and download **Oracle Database 19c for LINUX ARM (aarch64)** file.

---

### 2. Clone Repository oracle/docker-images
```bash
git clone github.com/oracle/docker-images
```

---

### 3. Copy or Move the file
Copy or Move the download file ```LINUX.ARM64_1919000_db_home.zip``` to ```docker-images/OracleDatabase/SingleInstance/dockerfiles/19.3.0```.

---

### 4. Build the Image
Use terminal and navigate to ```docker-images/OracleDatabase/SingleInstance/dockerfiles```.

Build the docker image by runing the shell script:
```bash
./buildContainerImage.sh -v 19.3.0 -e
```
where
 - -v: for version
 - -e: for enterprise edition

---

### 5. List to check the images
```bash
docker images
```
The list must have an image ```docker/database``` with tag ```19.3.0-ee```.

---

### 6. Run the Docker Container
Run a docker container using the image:
```bash
docker run -d --name oracle19 -e ORACLE_PWD=mypassword1 -p 1521:1521 oracle/database:19.3.0-ee
```
where
  - --name: Name of the container
  - ORACLE_PWD: Password of your oracle database
  - -p: Port mapping

---

### 7. Check the status of the container
Check the status of the container: 
```bash
docker ps
```
The status should be ```healthy``` that means the container is up and running.

---

### 8. Download the VS Code Extension
Download the [Oracle SQL Developer Extension](https://marketplace.visualstudio.com/items?itemName=Oracle.sql-developer) for VSCode.
- Create a New Connection with the following properties
  ```text
  Name: SYS 
  (You can give anything, but I like to keep the connection name as the username, so that I know which user is using this connection.)

  Role: SYSDBA
  Username: SYS
  Password: mypassword1

  Hostname: localhost
  Port: 1521
  Type: Service Name
  Service Name: ORCLCDB
  ```

- Click on ```Test``` to check the connection
- Click on ```Save``` to save the connection
- Click on the connection name to connect, it will ask for the password
- Open a worksheet and run the SQL commands

---

# References
- [How to Install Oracle on an M1/M2 Mac (Finally)](https://www.youtube.com/watch?v=uxvoMhkKUPE)
- [Database Software Downloads | Oracle India](https://www.oracle.com/in/database/technologies/oracle-database-software-downloads.html)
- [oracle/docker-images: Official source of container configurations, images, and examples for Oracle products and projects](https://github.com/oracle/docker-images)
- [Oracle SQL Developer Extension for VSCode](https://marketplace.visualstudio.com/items?itemName=Oracle.sql-developer)