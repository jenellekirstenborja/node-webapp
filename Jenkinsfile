pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                linux-node
                }
            }
            steps {
                sh 'gradle --version'
            }
        }
    }
}
