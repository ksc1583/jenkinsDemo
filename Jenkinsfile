import java.text.SimpleDateFormat

pipeline {
    agent {
        label "demoAgent"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                build 'gitdemo2'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Prepare Today Date') {
            steps {
                 script {
                    def dateFormat = new SimpleDateFormat("yyyyMMdd")
                    def date = new Date()
                
                    today = dateFormat.format(date)                
                    
                }                
            } 
        }
        stage('Print Today Date') {
            steps {
                  echo today
            } 
    }
    post {
        always{
            echo 'pipeline done'
        }
    }
}
