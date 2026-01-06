# Jenkins – Complete Guide (CI/CD)

## Table of Contents

1. Introduction to Jenkins
2. What is CI & CD
3. Why Jenkins is Used
4. Jenkins Architecture
5. Jenkins Installation
6. Jenkins Terminology
7. Jenkins Dashboard Overview
8. Jenkins Job / Project Types
9. Jenkins Pipeline
10. Declarative vs Scripted Pipeline
11. Pipeline Skeletons
12. Jenkinsfile
13. Jenkins CI Workflow
14. Jenkins CD Workflow
15. Tools Integration with Jenkins
16. Jenkins Credentials Management
17. Jenkins Parameters
18. Jenkins Triggers
19. Jenkins Agents & Nodes
20. Jenkins Plugins
21. Jenkins Security
22. Jenkins Best Practices
23. Common Jenkins Errors & Fixes
24. Jenkins Interview Points
25. Conclusion

---

## 1. Introduction to Jenkins

Jenkins is an open-source automation server used to automate building, testing, and deploying applications. It is a core DevOps tool used to implement CI/CD pipelines.

---

## 2. What is CI & CD

### Continuous Integration (CI)

* Developers frequently push code to a shared repository
* Each commit triggers an automated build
* Code is compiled, tested, and validated automatically

### Continuous Deployment (CD)

* After CI success, code is automatically deployed
* Deployment can be to Dev, QA, Staging, or Production
* Reduces manual intervention and errors

---

## 3. Why Jenkins is Used

* Open source and free
* Huge plugin ecosystem
* Easy integration with DevOps tools
* Supports distributed builds
* Highly customizable

---

## 4. Jenkins Architecture

### Components

* Jenkins Master (Controller)
* Jenkins Agent (Node)
* Executor
* Workspace

### Flow

Developer → Git → Jenkins Master → Agent → Build/Test/Deploy

---

## 5. Jenkins Installation

### Prerequisites

* Java (JDK 11 or 17)
* Linux / Windows / Mac

### Basic Installation Commands (Linux)

```bash
sudo yum install java-17-amazon-corretto -y
wget https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum install jenkins -y
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

---

## 6. Jenkins Terminology

* Job / Project
* Build
* Workspace
* Executor
* Node / Agent
* Pipeline
* Jenkinsfile

---

## 7. Jenkins Dashboard Overview

* New Item
* Build History
* Manage Jenkins
* Credentials
* Nodes
* Plugins

---

## 8. Jenkins Job / Project Types

### Freestyle Job

* GUI based
* Simple projects

### Pipeline Job

* Code-based (Jenkinsfile)
* Recommended for CI/CD

### Multibranch Pipeline

* Automatically detects branches

### Folder

* Organize jobs

---

## 9. Jenkins Pipeline

Pipeline is a set of automated steps written as code.

### Benefits

* Version controlled
* Reusable
* Reliable

---

## 10. Declarative vs Scripted Pipeline

| Declarative       | Scripted       |
| ----------------- | -------------- |
| Easy syntax       | Flexible       |
| Opinionated       | Groovy based   |
| Beginner friendly | Advanced users |

---

## 11. Pipeline Skeletons

### Declarative Pipeline Skeleton

```groovy
pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        echo 'Checkout code'
      }
    }
    stage('Build') {
      steps {
        echo 'Build application'
      }
    }
    stage('Test') {
      steps {
        echo 'Run tests'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploy application'
      }
    }
  }
  post {
    success { echo 'Build Successful' }
    failure { echo 'Build Failed' }
  }
}
```

### Scripted Pipeline Skeleton

```groovy
node {
  stage('Checkout') {
    echo 'Checkout code'
  }
  stage('Build') {
    echo 'Build application'
  }
  stage('Test') {
    echo 'Run tests'
  }
  stage('Deploy') {
    echo 'Deploy application'
  }
}
```

### Parallel Stage Pipeline

```groovy
pipeline {
  agent any
  stages {
    stage('Testing') {
      parallel {
        stage('Unit Tests') {
          steps { echo 'Unit tests' }
        }
        stage('Integration Tests') {
          steps { echo 'Integration tests' }
        }
      }
    }
  }
}
```

---

## 12. Jenkinsfile

* Stored in project repository
* Defines CI/CD pipeline
* Written in Groovy

---

## 13. Jenkins CI Workflow

1. Developer commits code
2. Git webhook triggers Jenkins
3. Jenkins pulls code
4. Build executed
5. Tests executed
6. Reports generated

---

## 14. Jenkins CD Workflow

1. CI success
2. Artifact created
3. Artifact stored (Nexus/S3)
4. Deployment triggered
5. Application deployed

---

## 15. Tools Integration with Jenkins

* Git / GitHub
* Maven / Gradle
* SonarQube
* Nexus / Artifactory
* Docker
* Kubernetes
* AWS
* Slack

---

## 16. Jenkins Credentials Management

* Global credentials
* Username & password
* SSH keys
* Tokens
* Secrets

---

## 17. Jenkins Parameters

### Types

* String
* Choice
* Boolean
* Password

### Example

```groovy
parameters {
  string(name: 'ENV', defaultValue: 'dev')
}
```

---

## 18. Jenkins Triggers

* SCM Polling
* Webhook
* Build periodically
* Manual trigger

---

## 19. Jenkins Agents & Nodes

* Master assigns jobs
* Agents execute jobs
* Static agents
* Dynamic agents (Docker/K8s)

---

## 20. Jenkins Plugins

* Git Plugin
* Pipeline Plugin
* Maven Plugin
* Docker Plugin
* Slack Plugin
* Blue Ocean

---

## 21. Jenkins Security

* Authentication (LDAP, Local)
* Authorization (RBAC)
* Credentials masking
* Role-based access

---

## 22. Jenkins Best Practices

* Use Pipeline as Code
* Store Jenkinsfile in Git
* Use credentials securely
* Clean workspaces
* Limit plugins

---

## 23. Common Jenkins Errors & Fixes

### Java not found

Fix JAVA_HOME

### Permission denied

Fix file ownership

### Agent offline

Check connectivity

### Plugin failure

Update or rollback plugin

---

## 24. Jenkins Interview Points

* Difference between CI & CD
* Jenkinsfile usage
* Pipeline vs Freestyle
* Declarative vs Scripted
* Role of plugins
* Jenkins architecture

---

## 25. Conclusion

Jenkins is a powerful CI/CD automation tool that enables DevOps teams to build, test, and deploy applications efficiently. Mastering Jenkins pipelines and integrations is essential for modern DevOps practices.





