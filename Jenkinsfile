pipeline {
    agent { dockerfile true }

    stages {

        stage ('Code') {
            steps {
                git url: 'https://github.com/khapratik/docker-jenkins.git', branch: 'master'
            }
        }

        stage ('Check Docker existance') {
            steps {
                echo 'Build & Test'
                sh 'docker --version'
            }
        }
        
        stage ('Build & Test') {
            steps {
                echo 'Build & Test'
                sh 'docker build -t docker-jenkins .'
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
