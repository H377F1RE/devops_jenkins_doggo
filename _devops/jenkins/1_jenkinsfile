pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Docker Compose Up') {
            steps {
                sh """
                    cd _devops/docker_compose
                    docker compose -f docker-compose.yaml up -d --build
                """
            }
        }

        stage('Docker Compose Down') {
            when {
                expression { return params.STOP_AFTER_DEPLOY == 'true' }
            }
            steps {
                sh """
                    cd _devops/docker_compose
                    docker compose down
                """
            }
        }
    }
}