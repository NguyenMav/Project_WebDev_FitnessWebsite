pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    npm ci
                    npm run build
                '''
            }
        }

        stage('Test') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }

            steps {
                sh '''
                    ls -la test 
                    npm test 
                '''
            }
            post {
                always {
                    junit '**/test-results.txt' 
                }

                success {
                    echo 'All tests passed successfully.'
                }

                failure {
                    echo 'Some tests failed. Check the logs above for details.'
                }
            }
        }
    }
}
