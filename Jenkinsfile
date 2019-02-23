pipeline{
    agent { 
        label 'docker'
    }
    
    stages{
        stage('checkout'){
            steps{
                // git url: 'https://github.com/sonaikar/DevopsJan2019Nginx.git', branch: 'master'
                checkout scm
            }
        }
        
        stage('build image'){
            steps{
                sh 'docker build -t "docker.artifactory.cetdevops.com/webserver:${BUILD_NUMBER}" .'
            }
            
        }
        
        stage('upload image'){
            steps{
                 sh 'docker push "docker.artifactory.cetdevops.com/webserver:${BUILD_NUMBER}"'
            }
        }
    }
}
