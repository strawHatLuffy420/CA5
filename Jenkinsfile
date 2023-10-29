pipeline {
    agent any

    stages {
        stage('Check Docker Images') {
            steps {
                script {
                    def frontendImageExists = sh(script: "docker pull starwhatluffy/docker-whale:latest && echo 'Image exists'", returnStatus: true) == 0
            

                    
                }
            }
        }

        stage('Deploy Services with Docker Compose') {
            steps {
                script {
                    sh "docker-compose -f your-compose-file.yml up -d"
                }
            }
        }
    }

    post {
        always {
            // Clean up: Stop and remove containers if needed
            sh "docker-compose -f your-compose-file.yml down"
        }
    }
}

