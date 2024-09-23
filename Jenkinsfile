node {
    checkout scm
    def testImage = docker.build("jenkins/jenkins", "./dockerfiles/test") 

    testImage.inside {
        sh 'make test'
    }
}
