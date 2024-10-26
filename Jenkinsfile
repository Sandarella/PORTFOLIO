pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Шаг клонирования репозитория
					echo 'Clone repo...'
                    checkout scm
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Шаг сборки проекта
					echo 'Building the project...'
                    sh 'mvn clean install' // Пример для проекта на Maven
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Шаг деплоя в указанную папку на компьютере
					echo 'Deploying to /path...'
                   // sh 'mkdir -p /Users/alexandrareshetnikova/Проекты/Portfolio/buildpath' 
                    sh 'cp -r target/* /Users/alexandrareshetnikova/Проекты/Portfolio/buildpath'
                }
            }
        }
    }

    post {
        success {
            echo 'Build and deploy successful!'
        }
        failure {
            echo 'Build or deploy failed!'
        }
    }
}
