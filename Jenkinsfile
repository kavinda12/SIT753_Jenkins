pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building with Maven'
               // bat 'mvn clean package'
            }
        }
        stage('Unit Tests') {
            steps {
                echo 'Running JUnit tests'
                //bat 'mvn test'  
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Scanning with SonarQube'
               // bat 'sonar-scanner'  
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Checking with OWASP Dependency-Check'
               bat 'dependency-check.sh --scan .' 
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to AWS EC2 (staging)'
               // bat 'scp target/*.jar user@staging-server:/app'  
            }
        }
        stage('Integration Tests') {
            steps {
                echo 'Running Selenium tests on staging'
              // bat  'mvn verify -Pstaging-tests'  
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to AWS EC2 (production)'
               // bat 'scp target/*.jar user@prod-server:/app'  
            }
        }
    }
}
