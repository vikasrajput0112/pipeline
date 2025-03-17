pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/vikasrajput0112/pipeline.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    load 'ci/Jenkinsfile'
                }
            }
        }
    }
}
