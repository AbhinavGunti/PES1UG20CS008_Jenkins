pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o hello he.cp'
            }
        }

        stage('Test') {
            steps {
                sh './hello'
            }
        }

        stage('Deploy') {
            steps {
                echo 'SUCCESSFULLY DEPLOYED'
            }
        }
    }

    post {
        always {
            script {
                if (currentBuild.result == 'FAILURE') {
                    echo 'PIPELINE FAILED'
                }
            }
        }
    }
}