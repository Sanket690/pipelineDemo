pipeline {
    agent any

    //environment {
        // Set any environment variables needed for your build process (e.g., Java, Maven, etc.)
        //PATH = "C:\\Program Files\\Java\\jdk-18\\bin;${env.PATH}"
    //}

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository from GitHub
                git branch: 'master', url: 'https://github.com/Sanket690/pipelineDemo.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Run Maven build (change this if you're using another tool)
                    bat 'mvn clean package'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run Maven tests (change this if you're using another testing framework)
                    bat 'mvn test'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application on Windows...'
                // You can add deployment steps here, e.g., to copy files, deploy to servers, etc.
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed!'
        }
        success {
            echo 'Build and test succeeded!'
        }
        failure {
            echo 'Build or test failed!'
        }
    }
}
