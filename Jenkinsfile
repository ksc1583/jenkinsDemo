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
                 // java 라이브러리를 이용하여 날짜를 구한다 
                 script {
                    def dateFormat = new SimpleDateFormat("yyyyMMdd")
                    def date = new Date()
                
                    today = dateFormat.format(date)                
                    
                }                
            } 
        }
        stage('Print Today Date') {
            steps {
                  // Prepare Today Date 에서 구한 today 날짜 를 출력한다.
                  echo today
            } 
    }
    post {
        always{
            echo 'pipeline done'
        }
    }
}
