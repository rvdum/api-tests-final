pipeline {
    agent any
    triggers{ 
        pollSCM('*/1 * * * *') 
    }
    stages {
        stage('Build and push Docker image') {
            steps {
                script{
                    buildAndPush()
            }
        }
    }
}
}

def buildAndPush(){
    echo "Building of api-tests-final docker image starting.."
    sh "docker build -t radud1337/api-tests:latest ."
    
    echo "Pushing image to docker registry..."
    sh "docker push radud1337/api-tests:latest"
    echo "Building of api-tests-final docker image finished.."
}