pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/mohityadav643/comp2.git', branch: 'master'
            }
        }

        stage('Build and Deploy') {
            steps {
                script {
                    // Use hyphenated docker-compose
                    sh 'docker-compose down || true'
                    sh 'docker-compose pull'
                    sh 'docker-compose up -d --build'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished successfully'
        }
    }
}
