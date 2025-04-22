pipeline {
    agent any

    environment {
        PATH = "/usr/bin:/usr/local/bin:$PATH" // Ensure node & npm are in the path
    }

    stages {
        stage('Pull from GitHub') {
            steps {
                git url: 'https://github.com/kavya-2004-04/cicd-aws-project.git', branch: 'main'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Application') {
            steps {
                sh 'npm run build || echo "No build script defined. Skipping..."'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/*', fingerprint: true
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step here (e.g., upload to S3 or copy to server)'
                // Example for S3:
                // sh 'aws s3 cp ./dist s3://cicd-pipeline33/ --recursive'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs.'
        }
    }
}
