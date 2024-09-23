pipeline {
    agent linux-node

    
    stages {
        stage('Build and Test') {
            when {
                expression { !infra.isTrusted() }
            }

            parallel {
                stage('Windows') {
                    agent {
                        label "docker-windows"
                    }
                    steps {
                        bat "powershell -File ./make.ps1 -Target build"
                    }
                }
                stage('Linux') {
                    agent {
                        label "docker&&linux"
                    }
                    steps {
                        sh "make lint"
                        sh "make build"
                        sh "make test"
                    }
                }
            }
        }
