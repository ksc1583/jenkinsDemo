import java.text.SimpleDateFormat


pipeline {
    agent{
        label "demoAgent"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                 script {
                    def dateFormat = new SimpleDateFormat("yyyyMMdd")
                    def date = new Date()
                
                    today = dateFormat.format(date) 
            }
        }
        stage('Test') {
            steps {
                build 'gitdemo2'
                echo today
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
        always {
            echo "pipeline job done!!!"
        }
    }
}
