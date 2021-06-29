pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                nodejs(nodeJSInstallationName: 'nodejs'){
                    sh 'npm install'
                    sh 'npm run build'
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