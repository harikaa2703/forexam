# forexam

## Maven Dependencies

```xml
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-api</artifactId>
    <version>5.11.0</version>
    <scope>test</scope>
</dependency>

<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-engine</artifactId>
    <version>5.11.0</version>
    <scope>test</scope>
</dependency>
```

---

## Docker

```dockerfile
FROM redis:latest
CMD ["redis-server"]
```

### 1.

```bash
docker build -t redisnew
```

### 3.

```bash
docker run --name myredisnew -d redisnew
```

### 5.

```bash
docker ps
```

### 7.

```bash
docker stop myredisnew
```

### 9.

```bash
docker login
```

### 11.

```bash
docker ps -a
```

### 13.

```bash
docker commit 0e993d2009a1 budarajumadhurika/redis1
```

### 14.

```bash
docker images
```

### 15.

```bash
docker push budarajumadhurika/redis1
```

### 16.

```bash
docker rm 0e993d2009a1
```

### 17.

```bash
docker rmi budarajumadhurika/redis1
```

### 19.

```bash
docker logout
```

### 20.

```bash
docker pull budarajumadhurika/redis1
```

### 21.

```bash
docker run --name myredis -d budarajumadhurika/redis1
```

### 23.

```bash
docker exec -it myredis redis-cli
SET name "Abcdef"
GET name
exit
```

### What It Does:

• Logs you out from Docker Hub and removes your stored credentials.

---

## Docker Web App

```bash
nano Dockerfile
docker build -t mywebapp .
docker run -p 8080:8080 mywebapp
docker images
docker commit <container-id> <username>/mywebapp
docker push <username>/mywebapp
```

## Git

```bash
git init
git add .
git commit -m "push"
git remote add origin <repo-URL>
git push -u origin main
```

---

## Dockerfiles

### Web Application

```dockerfile
FROM tomcat:9
COPY target/*.war /usr/local/tomcat/webapps/
COPY target/*.war /usr/local/tomcat/webapps/
```

### Java Application

```dockerfile
FROM eclipse-temurin:17
COPY target/*.jar app.jar
CMD ["java", "-jar", "app.jar"]
```

### Web Application - ROOT

```dockerfile
FROM tomcat:9.0
COPY target/*.war /usr/local/tomcat/webapps/ROOT.war
CMD ["catalina.sh","run"]
```

---

## Maven POM

```xml
<?xml version="1.0" encoding="UTF-8"?>

<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                             http://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.kmit.calculator</groupId>

    <artifactId>simple-cal</artifactId>

    <version>0.0.1-SNAPSHOT</version>

    <packaging>war</packaging>

    <name>Simple Calculator</name>

    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.release>11</maven.compiler.release>
    </properties>

    <dependencies>

        <!-- JUnit dependency -->
        <dependency>
            <groupId>org.junit.jupiter</groupId>

            <artifactId>junit-jupiter-api</artifactId>

            <version>5.11.0</version>
            <scope>test</scope>
        </dependency>

        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-engine</artifactId>
            <version>5.11.0</version>
            <scope>test</scope>
        </dependency>

    </dependencies>

    <build>

        <plugins>

            <!-- Compiler Plugin -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>

                <artifactId>maven-compiler-plugin</artifactId>

                <version>3.13.0</version>

                <configuration>
                    <release>11</release>
                </configuration>
            </plugin>

            <!-- JAR Plugin -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-jar-plugin</artifactId>

                <version>3.4.2</version>

                <configuration>
                    <archive>
                        <manifest>
                            <mainClass>com.kmit.simple_cal.Calculator</mainClass>
                        </manifest>
                    </archive>
                </configuration>
            </plugin>

            <!-- Clean Plugin -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-clean-plugin</artifactId>
                <version>3.4.0</version>
            </plugin>

        </plugins>

    </build>

</project>
```

---

## Useful Docker Commands

### 1)Check logs after an app crashes

```bash
docker logs <container_name>
```

### 2)Find which container is using port 3000

```bash
docker ps --filter "publish=3000"
```

### 3) Tag an image that you forgot to tag

```bash
docker tag <existing-image> <new-name>:<tag>
```

### 4)Export an image as .tar

```bash
docker save -o myimage.tar myimage
```

### 5)Automatically restart a container if it crashes

When creating the container:

```bash
docker run --restart=on-failure <image_name>
```

If the container already exists, you can set the restart policy with:

```bash
docker update --restart=on-failure <container_name>
```

### 6)How to limit RAM?

```bash
docker run --memory=512m <image_name>
```

### 7)

```bash
docker tag redisi:latest harika2703/redisi:latest
```

-------------perform this for evry push ,before push perform this

---

## Git Commands

### 1)

```bash
git remote remove origin
```

### 2)

```bash
git fetch <remote_name>
```

### 3)

```bash
git remote set-url origin https://github.com/username/new-repository.git
```

### 4)

```bash
git remote show origin
```

### 5)

```bash
git branch –r
```

---------all remote branches

### 6)

```bash
git rebase origin/main
```

“Take my local commits and replay them on top of the latest origin/main

### 7)

Shows the details of a specific commit, including the changes made and the commit message.

```bash
git show <commit>
```

### 8)Recovering deleted branches

```bash
git reflog
git checkout -b feature-ui <commit_hash>
```

### 9)To download the latest changes from the remote without merging

```bash
git fetch origin
```

### 10) To remove accidentally committed sensitive file from Git history.

```bash
git filter-branch --force --index-filter \
"git rm --cached --ignore-unmatch secrets.txt" \
--prune-empty --tag-name-filter cat -- --all
```

### 11)Add Rules to .gitignore

Inside the .gitignore file, you add patterns for the files and directories you want Git to ignore. Each pattern should be written on a new line.

Here are some common examples:

• Ignore all .log files:

```gitignore
*.log
```

• Ignore a specific file:

```gitignore
secret_file.txt
```

• Ignore all files in a temp/ directory:

```gitignore
temp/
```

• Ignore all files except important_file.txt inside a folder:

```gitignore
folder/*
!folder/important_file.txt
```

• Ignore files with a specific extension:

```gitignore
*.bak
```

### 12)16. Git stash

```bash
git stash
git switch another-branch
# do something else...
git switch main
git stash apply
```

### 13)To check branch is merge

```bash
git branch –merged
```

If branch not merged then displays its name

### Restore stashed changes

```bash
git stash pop
```

### 14)Remove a file from staging without losing changes

```bash
git restore --staged file1.txt
```

### 15)Create search-filter from main

While on main:

```bash
git switch -c search-filter
```

### 16)Remove an API key completely from repository history

Simply deleting the file is not enough, because the key remains in Git history.

Use history-rewriting tools such as:

```bash
git filter-repo
```
