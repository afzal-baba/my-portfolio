# Afzal - Portfolio V2

> Minimal DevOps Portfolio - Java JSP + Maven + Jenkins + Tomcat 10

![Java](https://img.shields.io/badge/Java-21-orange)
![Maven](https://img.shields.io/badge/Maven-3.9-blue)
![Tomcat](https://img.shields.io/badge/Tomcat-10.1.59-yellow)
![Jenkins](https://img.shields.io/badge/Jenkins-CI%2FCD-red)
![License](https://img.shields.io/badge/License-MIT-green)

Live Demo: `http://localhost:8082/portfolio/`

### ✨ Preview
**Afzal - Portfolio V2**
DevOps Engineer | Mock Interview Prep

**My Skills:** Java, Docker, Jenkins, Kubernetes

Clean centered UI with lavender background `#F0F3FF`, deep blue heading `#23408E`, and white rounded card.

---

### 🚀 Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | JSP, HTML5, CSS3 |
| Backend | Java 21 (Jakarta Servlet 5.0) |
| Build | Maven (war: `portfolio.war`) |
| CI/CD | Jenkins Pipeline |
| Server | Apache Tomcat 10.1.59 |
| VCS | Git & GitHub |

### 📁 Project Structure

```bash
my-portfolio/
├── src/main/webapp/
│   ├── index.jsp          # Main portfolio page (V2 design)
│   └── css/
│       └── style.css      # Lavender background + card styling
├── pom.xml                # Maven config - jakarta.servlet-api
├── Jenkinsfile            # Build & Deploy pipeline
└── README.md
```

### 🛠️ Local Setup

1. **Clone**
```bash
git clone https://github.com/afzal-baba/my-portfolio.git
cd my-portfolio
```

2. **Build WAR**
```bash
mvn clean package
```
Output: `target/portfolio.war`

3. **Deploy to Tomcat**
```bat
copy target\portfolio.war "C:\devops\apache-tomcat-10.1.59\webapps\" /Y
```
Tomcat will auto-extract to `/portfolio/`

4. **Run**
```
http://localhost:8082/portfolio/
```

### 🔄 Jenkins CI/CD

This project uses Jenkins pipeline:

```groovy
pipeline {
    agent any
    stages {
        stage('Build WAR') {
            steps { bat 'mvn clean package' }
        }
        stage('Deploy to Tomcat') {
            steps {
                bat '''
                rmdir /S /Q "C:\\devops\\apache-tomcat-10.1.59\\webapps\\portfolio"
                del /Q "C:\\devops\\apache-tomcat-10.1.59\\webapps\\portfolio.war"
                copy target\\portfolio.war "C:\\devops\\apache-tomcat-10.1.59\\webapps\\" /Y
                '''
            }
        }
    }
}
```

Workflow: `Git Push -> Jenkins Trigger -> Maven Build -> Tomcat Deploy -> Live`

### 🎨 Visual Design (V2)

- **Background:** `#F0F3FF` - soft lavender
- **Heading:** `#23408E` - bold centered
- **Card:** White, 12px radius, soft shadow `0 2px 15px rgba(0,0,0,0.07)`
- **Layout:** Flex center, single column, 400px card, responsive
- **Font:** Segoe UI / Inter, minimal & interview-ready

### 🐛 Common Issues Fixed

- `Unknown tool type "maven"` -> Use `maven 'maven3'` lowercase
- Tomcat 10 404 -> Use `jakarta.servlet-api` not `javax.servlet`
- Empty WAR 404 -> Folder must be `src/main/webapp` not `scr/main/webapp`
- Old war locked -> Delete old `portfolio` folder + war before copy

### 📌 Roadmap

- [x] V2 - Minimal JSP Portfolio
- [x] Jenkins CI/CD
- [ ] V3 - Add Projects & Contact Section
- [ ] Dockerize with `tomcat:10-jdk21`
- [ ] Deploy to AWS EC2 / Kubernetes

### 👤 Author

**Afzal Baba**
DevOps Engineer | Mock Interview Prep
- GitHub: [@afzal-baba](https://github.com/afzal-baba)
- Portfolio: `localhost:8082/portfolio/` (local)

### 📄 License

MIT License - feel free to fork for your own portfolio.

---
⭐ If you like this minimal portfolio template, give it a star!
