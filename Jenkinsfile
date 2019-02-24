pipeline{
    agent { 
        label 'docker'
    }
    
    stages{
        stage('checkout'){
            steps{
                git url: 'https://github.com/sonaikar/DevopsJan2019Nginx.git', branch: 'master'
                // heckout scm
            }
        }
        
        stage('build image'){
            steps{
                sh "echo Branch name is Brijesh"
                sh 'docker build -t "docker.artifactory.cetdevops.com/webserver:${BUILD_NUMBER}" .'
            }
            
        }
        
        stage('upload image'){
            steps{
                // script{
                //     env.ARTIFACTDEPLOY = input message: 'User input required',
                //     ok: 'Deploy!',
                //    parameters: [choice(name: 'Artifact to deploy', choices: "zip\ndockerimage\nrpm", description: 'Which artifact you wont deploy?')]
                // }
                // sh "echo ${ARTIFACTDEPLOY}"
                sh 'docker push "docker.artifactory.cetdevops.com/webserver:${BUILD_NUMBER}"'
            }
        }


    }
}
