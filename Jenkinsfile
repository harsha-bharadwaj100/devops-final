pipeline {
    agent any

    tools {
        jdk 'JDK21'
        maven 'Maven3'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/harsha-bharadwaj100/devops-final'
            }
        }

        stage('Build & Test with Coverage') {
            steps {
                bat 'mvn clean test'
            }
        }
    }

    post {
        always {
			junit '**/target/surefire-reports/*.xml'
			archiveArtifacts artifacts: 'target/site/jacoco/**', fingerprint: true
		}
    }
}