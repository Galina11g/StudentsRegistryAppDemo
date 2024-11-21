pipeline{
    agent any

 
    stages {
        stage('Checkout'){
            steps{
                git branch: 'master', url: 'https://github.com/Galina11g/StudentsRegistryAppDemo'
            }
        }
        stage('Install Dependencies') {
            steps {
                script{
                    bat 'npm install'
                }
                
            }
        }
        stage('Start Application') {
            steps {
                script{
                    bat 'start /b npm start'
                    
                }
            }
        }
         stage('Run Tests') {
            steps {
                script{
                    bat 'npm test'
                }
            }
        }
    
    }
    post {
        always {
            echo 'CI Pipeline completed.'
        }
    }
}
