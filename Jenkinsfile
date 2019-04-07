pipeline {
    agent any
    tools {
            maven 'Maven 3.6'
        }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh "mvn clean compile"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh "mvn test"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh "mvn -DSkipTests package"
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}