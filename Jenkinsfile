pipeline {
    agent any
    stage{
        stage('Prepare artifacts'){
            steps{
                sh '''
                  mkdir publish
                  cp -r static publish
                '''
            }
        }
        stage('publish artifacts'){
            steps {
                sh '''
                   cd publish
                   az artifacts universal download --organization https://dev.azure.com/nikkaushal0032/
                   --project="devops-practise" --scope project --feed devops0032 --name frontend --version 0.0.22--path .
                '''
            }
        }
    }
}