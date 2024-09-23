node {
    checkout scm

    def customImage = docker.build("jenkins/jenkins")

    customImage.inside {
        sh 'make test'
    }
}
