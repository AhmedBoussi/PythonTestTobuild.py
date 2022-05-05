pipeline {
    agent none // (1)
    stages {
        stage('Build') { // (2)
            agent {
                docker {
                    image 'python:3-alpine' // (3)
                }
            }
            steps {
                sh 'python -m py_compile sources.py' // (4)
                
            }
        }
        stage('Test') {
            agent {
                docker {
                    image 'qnib/pytest'
                }
            }
            steps {
                sh 'py.test --verbose --junit-xml test-reports/results.xml sources/test_calc.py'
            }
    }
}
