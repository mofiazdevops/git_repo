pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your GitHub repository
                git branch: 'main', url: 'https://github.com/mofiazdevops/git_repo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                // Build the Docker image
                script {
                    def image = docker.build("hacker")
                }
            }
        }

        stage('Run Container') {
            steps {
                // Run the Docker container
                script {
                    docker.image("hacker").run('-p 80:80')
                }
            }
        }
    }
}
