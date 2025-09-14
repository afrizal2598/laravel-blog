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
        
        // stage('Testing Application') {
        //     steps {
        //         sh '''
        //         composer install --dev --optimize-autoloader
        //         composer require fakerphp/faker --dev
        //         php artisan test
        //         '''
        //     }
        // }
         stage('Build Container Image') {
            steps {
                sh '''
                docker compose build
                '''
            }
        }
         stage('Build Container Application') {
            steps {
                echo 'Build Container Application'
            }
        }
        stage('Publish Container Image') {
            steps {
                echo 'Publish Container Image'
            }
        }
    }
}
