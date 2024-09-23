pipeline {
    agent {
        label 'linux-node'
    }
    
    stages {
        stage('Build') {
            steps {
                git branch: "master",
                    url: "https://github.com/jenellekirstenborja/node-webapp.git"
                
                sh 'docker build -t jenkins/jenkins .'
                sh 'docker push jenkins/jenkins'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -p 8080:8080 -v ~/jenkins_home:/var/jenkins_home -d --name jenkins-server jenkins/jenkins:lts-jdk17'
            }
        }

    }
}
