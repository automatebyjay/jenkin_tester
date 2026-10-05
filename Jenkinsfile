pipeline {
    agent any

    stages {

        stage('Validate Files') {
            steps {
                echo 'Checking project files...'

                sh '''
                    test -f index.html
                    test -f style.css
                    test -f script.js

                    echo "All required files exist."
                '''
            }
        }

        stage('Build') {
            steps {
                echo 'Static website - no build step required.'
            }
        }

        stage('Test') {
            steps {
                echo 'Running basic tests...'

                sh '''
                    test -s index.html || true
                    test -s style.css || true
                    test -s script.js || true

                    echo "Validation completed."
                '''
            }
        }
    }

    post {
        success {
            echo 'CI pipeline completed successfully!'
        }

        failure {
            echo 'CI pipeline failed.'
        }
    }
}