pipeline {
    agent any  // Use any available agent

    tools {
        maven 'VishwasMaven'  //
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/vishwaspw/addNumbers.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Run Maven build
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // Run unit tests
            }
        }

        stage('Run Application') {
            steps {
                // Start the JAR application (adjust JAR name if necessary)
                sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
