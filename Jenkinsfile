pipeline {
    agent any
    stages {
        stage('Build WAR') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                bat 'copy target\\portfolio.war "C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps\\" /Y'
            }
        }
    }
}

