pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'Git Hub Uname and owd', url: 'https://github.com/ArjunR0I/javappproject.git'
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t spring-hello .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8080:9090 --name hello-app spring-hello'
            }
        }
    }
}
