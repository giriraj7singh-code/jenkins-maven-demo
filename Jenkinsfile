pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building Maven application...'
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying JAR...'
                sh 'cp target/*.jar /opt/deployed-app/'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}
