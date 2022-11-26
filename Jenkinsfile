pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                git credentialsId: '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', 
                url: 'https://github.com/kejkara/mynewrepo_08Nov2022.git',
                branch: 'amitdev'
            }
        }
        stage('build') {
            steps {
                sh '''echo 'Build docker image'
                docker build . -t todoapp:v2'''
            }
        }
        stage('Run') {
            steps {
              sh '''echo "running the application"
                docker run -d -p 8000:8000 todoapp:v2'''
            }
    }
}
}
