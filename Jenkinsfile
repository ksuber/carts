pipeline {
    agent any
    tools {
            maven 'Maven 3.6'
        }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh "maven clean compile"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh "maven test"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh "maven -DSkipTests package"
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}