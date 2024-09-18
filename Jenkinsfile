pipeline {
    agent none
    stages {
         stage('Maven Clean') {
            agent {
                docker {
                    image 'maven:3.8.6-openjdk-11'
                }
            }
            steps {
                sh 'mvn clean'
            }
        }

        stage('Build with Maven') {
            agent {
                docker {
                    image 'maven:3.8.6-openjdk-11'
                }
            }
            steps {
                sh 'mvn package'
            }
        }

        stage('Run Spring Boot Application') {
            agent {
                docker {
                    image 'maven:3.8.6-openjdk-11'
                }
            }
            steps {
                sh 'mvn spring-boot:run -Dspring-boot.run.arguments=--server.port=8081'
            }
        }
    }
}

