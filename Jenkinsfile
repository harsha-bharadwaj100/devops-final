pipeline {
agent any
tools {
jdk 'JDK21'
maven 'Maven3'
}
stages {
stage('Checkout') {
steps {
git 'https://github.com/harsha-bharadwaj100/devops-final'
}
}
stage('Build') {
steps {
bat 'mvn clean compile'
}

}
stage('Test') {
steps {
bat 'mvn test'
}
}
}
post {
always {
junit '**/target/surefire-reports/*.xml'
}
}
}