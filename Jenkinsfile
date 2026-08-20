pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Maven application...'
                sh 'mvn clean package'
            }
        }

        stage('Use Credential') {
            steps {
                withCredentials([
                    string(
                        credentialsId: 'demo-secret',
                        variable: 'MY_SECRET'
                    )
                ]) {
                    sh 'echo "Credential successfully loaded into Jenkins"'
                }
            }
        }
    }
}
