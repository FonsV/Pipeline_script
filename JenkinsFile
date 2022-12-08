pipeline {
    
    agent any
    
    stages {
               
        stage('Build') {
            steps {
                echo "Building the checked-out project"
                sh 'sh Build.sh'
            }
        }
        
        stage('Unit_Test') {
            steps {
                echo "Running JUnit tests"
                sh 'sh Unit.sh'
            }
        }
        
        stage('Quality_Gate') {
            steps {
                echo "verifying Quality gates"
                sh 'sh Quality.sh'
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deploying to stage environment for more tests!"
                sh 'sh Deploy.sh'
            }
        }
    }
    
    post {
        
        always {
            echo "This will always run"
        }
        
        success {
            echo "This will run if successful"
        }
        
        failure {
            echo "This will run if failure"
        }
        
        unstable {
            echo "This will run if unstable"
        }
        
        changed {
            echo "This will run if state of the pipeline has changed"
        }
    }
    
}
