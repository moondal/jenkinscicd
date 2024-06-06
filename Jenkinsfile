pipeline {
    agent any
    tools {
        maven 'maven-3.8.1'
    }    

    stages {
        stage('Hello') {
            steps {
                sh "mvn clean package"
            }
        }
    }
}
