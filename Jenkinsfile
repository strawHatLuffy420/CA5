pipeline {
    agent any

    stages {
i190520
        stage('Build Docker Image') {
            steps {
                script {
                    def imageName = 'strawhatluffy/web-server-image:latest'
                    docker.build(imageName, '-f Dockerfile .')

                    // Push the image to Docker Hub or another container registry
                    docker.withRegistry('https://hub.docker.com/repository/docker/strawhatluffy420/webserver-image/general', 'strawhatluffy420') {
                        docker.image(imageName).push()
                    }
                }
            }
        }
    }
}

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

main
