#  Jenkins Demo Project

This repository demonstrates how to integrate **Jenkins**, **GitHub Actions**, and **Maven** for building and automating a Java project.

---

##  Overview

This project shows:

* CI/CD using Jenkins
* Automation using GitHub Actions
* Build management using Maven
* Basic pipeline and workflow syntax

---

##  Tech Stack

* Java
* Maven
* Jenkins
* GitHub Actions

---

##  Maven Build

To build the project using Maven:

```bash
mvn clean install
```

###  `pom.xml` (Basic Structure)

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" ...>
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.demo</groupId>
  <artifactId>jenkins-demo</artifactId>
  <version>1.0-SNAPSHOT</version>

  <dependencies>
    <!-- Add dependencies here -->
  </dependencies>
</project>
```

---

##  Jenkins Pipeline

###  `Jenkinsfile`

```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-username/jenkins-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
```

---

##  GitHub Actions Workflow

###  `.github/workflows/main.yml`

```yaml
name: Java CI with Maven

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Set up JDK
      uses: actions/setup-java@v3
      with:
        java-version: '17'

    - name: Build with Maven
      run: mvn clean install
```

---

##  How to Run

### Using Maven

```bash
mvn clean install
```

### Using Jenkins

1. Create a new pipeline job
2. Link this repository
3. Run the pipeline

### Using GitHub Actions

* Push code to `main` branch
* Workflow runs automatically

---

##  Features

* Automated build and test
* CI/CD pipeline integration
* Cross-platform automation
* Easy to extend

---

##  Contribution

Feel free to fork this repo and improve it!

---

##  Contact

Created by **Kavya M Injineri**
