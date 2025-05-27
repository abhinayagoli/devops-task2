# DevOps Task 2 - CI/CD Pipeline with Jenkins and Docker

This project demonstrates a basic CI/CD pipeline using *Jenkins* and *Docker* to build and deploy a simple static website.

## 🔧 Technologies Used
- Jenkins
- Docker
- GitHub
- Nginx
- HTML

## 🚀 What This Pipeline Does
1. Jenkins pulls the latest code from the GitHub repository.
2. Builds a Docker image using the provided Dockerfile.
3. Runs a Docker container to serve the static website on port 8081.

## 📁 Project Structure

## 🖥 Output
The deployed web page displays:
> *Hello from Abhinaya's CI/CD pipeline via Jenkins and Docker!*


## How to Install Jenkins (Using Docker on Windows)

### Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed on Windows
- WSL installed (Docker Desktop uses it)
- Git installed (optional for cloning repos)

---

### Step-by-Step: Run Jenkins in Docker

1. *Open CMD or PowerShell* as administrator

2. *Pull Jenkins Docker image*:
   bash
   docker pull jenkins/jenkins:lts
   

3. *Run Jenkins container*:
   bash
   docker run -d -p 8080:8080 -p 50000:50000 ^
     --name jenkins ^
     -v jenkins_home:/var/jenkins_home ^
     jenkins/jenkins:lts
   

4. *Open Jenkins in your browser*:  
   [http://localhost:8080](http://localhost:8080)

5. *Get Jenkins admin password*:
   bash
   docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
   

6. *Paste the password in the Jenkins UI* and follow the setup wizard

---

## How to Run the Pipeline

1. In Jenkins Dashboard, click *"New Item"*
2. Enter a name like devops-task2 and choose *"Pipeline"*
3. Scroll to *Pipeline* section
4. Set:
   - *Definition*: Pipeline script from SCM
   - *SCM*: Git
   - *Repository URL*:  
     https://github.com/abhinayagoli/devops-task2.git
   - *Script Path*: Jenkinsfile
5. Click *Save* and then *Build Now*

---

## Outcome

- Jenkins pulls the code from GitHub
- Builds Docker image
- Runs a container serving the HTML page at [http://localhost:8080](http://localhost:8080)

---
![Screenshot 2025-05-27 190233](https://github.com/user-attachments/assets/0da4931d-b659-43ac-8746-bbeb4d2f0984)
