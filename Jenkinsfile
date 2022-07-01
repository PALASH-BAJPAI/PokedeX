pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "sudo npm install"
                sh "sudo npm start" 
                             
            }
        }
          
        stage('Test') {
            steps {
                sh "sudo chmod a+x ./Jenkins/scripts/test.sh"
                sh "./Jenkins/scripts/test.sh "
                
            }
        }
          
        stage("Deploy") {
            steps {
                sh "sudo rm -rf /var/www/jenkins-react-app"
                sh "scp -r ${WORKSPACE}/build/* ubuntu@50.17.127.32:/var/www/jenkins-react-app/"
            }
        }
    }
}
