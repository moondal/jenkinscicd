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
                        docker.withRegistry('https://registry.hub.docker.com', 'moondalhyun-docker'){
                        image = docker.build("moondalhuyn/demo-springboot:${BUILD_NUMBER}")
                        image.push()
                    }
                }
            }
        }  
        stage('remove image') {
            steps {
                sh "docker rmi $image"
            }
        }              
    }
}
