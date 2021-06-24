pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                nodejs(nodeJSInstallationName: 'nodejs'){
                    sh 'npm install'
                }
            }            
        } 
        stage('desploy'){
            steps {
                nodejs(nodeJSInstallationName: 'nodejs'){
                    withAWS(credentials: 'aws-credentials'){
                        sh 'serverless deploy'
                    }
                }
            }
        }
    }
}