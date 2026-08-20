pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Maven application...'
                sh 'mvn clean package'
            }
        }
    }

    post {
        success {
            echo 'Maven build completed successfully!'
        }

        always {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}
