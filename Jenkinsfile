pipeline {
    agent any
    stages {
        stage('build') {
            steps{
                sh 'mvn --version'
                sh 'echo Hello, World'
                sh '''
                    echo "Multiple shell steps works too"
                    ls -lah
                '''
            }
        }
        post {
            always {
                echo 'This will always run'
            }
            success {
                echo 'This will run only if successful'
            }
            failure {
                echo 'This will run only if failed'
            }
            unstable {
                echo 'This will run only if the run was marked as unstavle'
            }
            changed {
                echo 'This will run only if the state of the Pipeline has changed'
                echo 'For example, if the Pipeline was previously failing but is now successful'
            }
        }
    }
}