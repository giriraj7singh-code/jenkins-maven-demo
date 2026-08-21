stages {

    stage('Environment Info') {
        steps {
            echo "Job Name: ${env.JOB_NAME}"
            echo "Build Number: ${env.BUILD_NUMBER}"
            echo "Workspace: ${env.WORKSPACE}"
            echo "Build URL: ${env.BUILD_URL}"
        }
    }

    stage('Build') {
        steps {
            echo "Building for ${params.ENVIRONMENT}"
            sh 'mvn clean package'
        }
    }

    stage('Deploy') {
        steps {
            echo "Deploying to ${params.ENVIRONMENT}"
            sh 'cp target/*.jar /opt/deployed-app/'
        }
    }
}
