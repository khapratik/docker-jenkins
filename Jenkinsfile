pipeline {
    agent { label 'dev' }

    stages {

        stage ('Code') {
            steps {
                git url: 'https://github.com/khapratik/docker-jenkins.git', branch: 'master'
            }
        }
        
        stage ('Build & Test') {
            steps {
                echo 'Build & Test'
                sh 'docker build . -t ajitfawade14/node-todo-app:latest'
            }
        }
        
        
        stage ('Deploy') {
            steps {
                echo 'Deploying'
                sh 'docker-compose down && docker-compose up -d'
            }
        }

    }
}
