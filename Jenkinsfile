pipeline{
    agent any 
    stages {
        stage("build"){
            steps{
                sh "npm install"   
            }
        }
        stage("run"){
            steps{
                script{  withEnv(['JENKINS_NODE_COOKIE=dontkill']) {
                    sh "npm run start:dev &"
                }
            }
            }
        
        }
        stage("test"){
            steps{
                sh "curl http://localhost:3000"
            }
        }
    }

}
