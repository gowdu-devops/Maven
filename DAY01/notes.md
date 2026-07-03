# 🔹 Development Flow

### **Developer → GitHub → Maven → Tomcat**

This is the typical Java application workflow:

1. **Developer**

   * Writes Java code on a local machine.
   * Uses **Linux**, **Shell scripting**, and **Git** for development and automation.

2. **Git**

   * Version control tool.
   * Tracks code changes locally.

3. **GitHub**

   * Remote repository hosting service.
   * Stores source code in the cloud.
   * Enables collaboration.

4. **Maven**

   * Builds the project.
   * Downloads dependencies.
   * Packages the project into `.jar`, `.war`, or `.ear`.

5. **Tomcat**

   * Application server.
   * Deploys and runs `.war` files.

Example Server:
Apache Tomcat

---

# 🔹 What is Build?

**Build** is the process of:

* Compiling source code
* Running tests
* Packaging into deployable files (JAR/WAR/EAR)

Build output examples:

* `.jar`
* `.war`
* `.ear`

---

# 🔹 What is Maven?

Apache Maven is:

* A **build automation tool**
* Developed by the **Apache Software Foundation**
* Open-source
* Platform-independent
* Mainly used for **Java projects**
* Not an executable (.exe)
* Distributed as **zip/tar.gz**
* Requires Java (JDK) installed

### Download Maven:

👉 [https://maven.apache.org/download.cgi](https://maven.apache.org/download.cgi)

---

# 🔹 Why Do We Use Maven?

Without Maven:

* Manually download JAR files
* Manually manage dependencies
* Complex build process

With Maven:

* Automatic dependency management
* Standard project structure
* Easy build lifecycle
* Integration with CI/CD tools
* Works well with GitHub & Jenkins

---

# 🔹 Popular Build Tools

## Java

* Ant
* Maven
* Gradle

## Python

* PyBuilder

## .NET

* MS Build
* Nant

## Ruby

* Rake

## Go

* go build tool

---

# 🔹 What is JAR, WAR, EAR?

## 1️⃣ JAR (Java Archive)

**Used for:** Standalone Applications

Contains:

* `.class` files
* Java libraries

Example:

```bash
java -jar app.jar
```

---

## 2️⃣ WAR (Web Archive)

**Used for:** Web Applications

Contains:

* Java code
* HTML
* CSS
* JavaScript
* Images
* JAR files

Deploys on:

* Apache Tomcat

---

## 3️⃣ EAR (Enterprise Archive)

**Used for:** Enterprise Applications

Contains:

* JAR
* WAR
* Modules
* Web content
* Enterprise components

Used in:

* Large enterprise servers (e.g., JBoss, WebLogic)

---

# 🔹 Maven Directory Structure (After Installation)

```
apache-maven-3.x.x/
│
├── bin/     → mvn command files
├── boot/    → runtime JAR files
├── conf/    → configuration files (settings.xml)
├── lib/     → library JAR files
```

---

# 🔹 Default Build Script File Names

| Tool   | File Name      |
| ------ | -------------- |
| Maven  | `pom.xml`      |
| Ant    | `build.xml`    |
| Gradle | `build.gradle` |

---

# 🔹 Maven Installation on Linux (EC2)

## ✅ System Requirements

* Maven 3.9+ requires **JDK 8 or above**
* Disk Space: ~10MB
* OS: Linux / Windows
* No minimum memory requirement

---

## 🔹 Step 0: Launch EC2 & Connect

Launch AWS EC2 Linux machine and connect via SSH.

---

## 🔹 Step 1: Switch to Root User

```bash
sudo su -
```

---

## 🔹 Step 2: Install Java (JDK 21)

Update system:

```bash
yum update -y
```

Check Java:

```bash
java -version
javac -version
```

Search Java packages:

```bash
sudo yum search java | grep -i openjdk
```

Install Java 21:

```bash
sudo yum install java-21-openjdk-devel -y
```

Verify:

```bash
java -version
javac -version
```

---

## 🔹 Step 3: Install Maven

### Pre-Requisite

✔ Java (JDK) must be installed

---

### 1️⃣ Go to /opt directory

```bash
cd /opt/
```

Install required packages:

```bash
yum install wget unzip tree git -y
```

---

### 2️⃣ Download Maven

```bash
wget https://dlcdn.apache.org/maven/maven-3/3.9.12/binaries/apache-maven-3.9.12-bin.zip
```

Unzip:

```bash
unzip apache-maven-3.9.12-bin.zip
```

---

### 3️⃣ Set Environment Variables

Edit profile:

```bash
vi ~/.bash_profile
```

Add:

```bash
export M2_HOME=/opt/apache-maven-3.9.12
export PATH=$PATH:$M2_HOME/bin
```

Reload profile:

```bash
source ~/.bash_profile
```

Check Maven:

```bash
mvn -version
```

Expected Output:

```
Apache Maven 3.9.12
Java version: 21
```

---

# 🔹 Complete DevOps Flow Example

```
Developer
   ↓
Write Code (Java)
   ↓
git add / commit
   ↓
Push to GitHub
   ↓
CI Tool (Jenkins)
   ↓
mvn clean package
   ↓
target/app.war
   ↓
Deploy to Tomcat
   ↓
Application Running
```

---

# 🔹 Important Maven Commands

```bash
mvn clean        # Deletes target folder
mvn compile      # Compiles code
mvn test         # Runs test cases
mvn package      # Creates JAR/WAR
mvn install      # Installs into local repo
mvn deploy       # Deploys to remote repo
```

---

# 🔹 Key Advantages of Maven

* Dependency management
* Standard directory structure
* Reproducible builds
* Easy integration with CI/CD
* Large plugin ecosystem

