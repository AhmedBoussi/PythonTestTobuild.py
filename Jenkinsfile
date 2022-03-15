pipline {
    agent none 
    stages('build'){
        agent{
            docker{
                image 'python:3-alpine'
            }
        }
        steps{
            sh 'python -m py_compile sources/*.py'

        }
    }
}
