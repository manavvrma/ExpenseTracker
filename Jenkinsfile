pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from version control
                git 'https://github.com/manavvrma/ExpenseTracker.git'
            }
        }
        
        stage('Compile') {
            steps {
                // Compile the Java code using Maven
                sh 'mvn compile'
            }
        }
        
        stage('Unit Test') {
            steps {
                // Run unit tests using Maven
                sh 'mvn test'
            }
        }
        
        stage('Generate Test Report') {
            steps {
                // Generate test report using Maven
                sh 'mvn surefire-report:report'
                junit '**/target/surefire-reports/*.xml'
            }
        }
        
        stage('Deploy') {
            steps {
                // Example deployment step, replace with actual deployment commands
                sh 'echo "Deploying..."'
            }
        }
    }
    
    post {
        always {
            // Cleanup steps, if necessary
            deleteDir()
        }
    }
}
