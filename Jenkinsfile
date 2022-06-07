pipeline {
    agent {
        label "demoAgent"
    }
    stages {
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
            
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                ech 'test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        
    }
    post {
        always{
            echo 'pipeline done'
        }
    }
}
