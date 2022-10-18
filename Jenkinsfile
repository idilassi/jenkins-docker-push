node {   
    stage('Clone repository') {
        git credentialsId: 'github-credentials', url: 'https://github.com/idilassi/jenkins-docker-push.git'
    }
    
    stage('Build image') {
       dockerImage = docker.build("idilassi/my-react-app:latest")
    }
    
 stage('Push image') {
        withDockerRegistry([ credentialsId: "credentilas-dockerhub", url: "https://github.com/idilassi/jenkins-docker-push.git" ]) {
        dockerImage.push()
        }
    }    
}
