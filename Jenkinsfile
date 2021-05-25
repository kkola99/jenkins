pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Sa incepem"
            }
        }
        stage('Deploy'){
        parallel {
            stage('Deploy start'){
            steps{
                echo "Start"
                sh "sudo -s yum install httpd -y"
                sh "sudo systemctl start httpd"
            }
            }
            stage('Deploying now'){
            agent any
            steps {
                sh "curl localhost:80"
            }
            }
        }
        }
    }
}
