pipeline {
    agent {label 'devops-01-afrizal'}

    stages {
        stage('Pull Source Code') {
            steps {
                git branch: 'main', url: 'https://github.com/afrizal2598/laravel-blog.git'
            }
        }
         stage('Testing Application') {
            steps {
                echo 'Testing Application'
            }
        }
         stage('Build Container Image') {
            steps {
                echo 'Build Container Image'
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
