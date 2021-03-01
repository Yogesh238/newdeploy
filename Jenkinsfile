pipeline {
agent any
tools {
maven 'maven'
}
stages {
stage('Git Checkout') {
steps {
git branch: 'main', credentialsId: 'e44652ce-bc38-4e73-861a-f9dc731c2a27', url: 'https://github.com/Yogesh238/newdeploy.git'
}
}
stage ('Clean') {
steps {
sh 'mvn clean'
}
}
stage ('Compile') {
steps {
sh 'mvn compile'
}
}
stage('Test') {
steps {
sh 'mvn test'
}
post {
always {
junit '**/target/surefire-reports/*.xml'
}
}
}
stage ('Package') {
steps {
sh 'mvn package'
}
}
}
}
