pipeline {
    agent {label 'devops-01-afrizal'}

    stages {
        stage('Pull Source Code') {
            steps {
                git branch: 'main', url: 'https://github.com/afrizal2598/laravel-blog.git'
            }
        }

        stage('Copy env variable') {
            steps {
               sh '''
                cp /usr/share/nginx/html/laravel-blog/.env .env
               '''
            }
        }

        stage('Code Quality Analysis') {
            steps {
                sh '''
              sonar-scanner \
                -Dsonar.projectKey=laravel-blog \
                -Dsonar.sources=. \
                -Dsonar.host.url=http://172.23.5.12:9000 \
                -Dsonar.token=sqp_95703c4fd1b1dba2e905ea4cfff6e3908bc1ca25
                '''
            }
        }

         stage('Build Container Image') {
            steps {
                sh '''
                docker compose build
                '''
            }
        }
         stage('Build Container Application') {
            steps {
                sh '''
                docker compose up -d
                '''
            }
        }
        stage('Publish Container Image') {
            steps {
               sh '''
                docker compose push
               '''
            }
        }
    }
}
