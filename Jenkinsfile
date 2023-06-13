pipeline {
    agent {
        label 'jenkins-ec2-fleet'
    } 
    stages {
        stage('Build') { 
            agent {
                docker {
                    label 'jenkins-ec2-fleet'
                    image 'python:2-alpine' 
                }
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py' 
                stash(name: 'compiled-results', includes: 'sources/*.py*') 
            }
        }
    }
}