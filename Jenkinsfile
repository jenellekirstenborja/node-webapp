node ('linux-node') {
    checkout scm
    def customImage = docker.build("jenkins/jenkins")
    customImage.inside {
        sh 'Inside Container'
        sh 'cat /etc/os-release'
    }
}
