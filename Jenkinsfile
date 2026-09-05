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
                bat '''
                rmdir /S /Q "C:\\devops\\apache-tomcat-10.1.59\\webapps\\portfolio"
                del /Q "C:\\devops\\apache-tomcat-10.1.59\\webapps\\portfolio.war"
                copy target\\portfolio.war "C:\\devops\\apache-tomcat-10.1.59\\webapps\\" /Y
                '''
            }
        }
    }
}
