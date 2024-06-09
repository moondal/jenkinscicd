pipeline {
    agent any
    tools {
        maven 'maven-3.8.1'
    }    

    stages {
        stage('build') {
            steps {
                sh "mvn clean package"
            }
        }
        stage('docker build') {
            steps {
                script {
                        docker.withRegistry('https://hub.docker.com', 'moondalhyun-docker'){
                        image = docker.build("moondalhuyn/demo-springboot:v2")
                        image.push()
                    }
                }
            }
        }        
    }
}