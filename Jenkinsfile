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
        stage('Start Application and Run Tests') {
            steps {
                script{
                    bat 'npm start &'
                    bat 'wait-on http://localhost:8090'
                    bat 'npm test'
                }
                
                
            }
        }
        post {
            always {
                echo 'CI Pipeline completed.'
            }
        
        }
    
    }
}
