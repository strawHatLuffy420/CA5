pipeline {
    agent any

    stages {
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
