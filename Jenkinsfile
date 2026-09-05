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
                bat 'copy target\\portfolio.war "C:\\devops\\apache-tomcat-10.1.59\\webapps\\" /Y'
            }
        }
    }
}
