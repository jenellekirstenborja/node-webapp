node {
     label 'linux-node'
     stage('clone repository') {
      checkout scm  
    }
     stage('Build docker Image'){
      app = docker.build("jenkins/jenkins")
    }
     stage('Test Image'){
       app.inside {
         sh 'echo "TEST PASSED"'
      }  
    }
     stage('Push Image'){
       docker.withRegistry('https://registry.hub.docker.com', 'git') {            
       app.push("${env.BUILD_NUMBER}")            
       app.push("latest")   
   }
}
