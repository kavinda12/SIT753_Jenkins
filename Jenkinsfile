pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building with Maven'
                bat 'mvn clean package'
            }
        }
        stage('Unit Tests') {
            steps {
                echo 'Running JUnit tests'
                /bat 'mvn test'  // Uncomment for real projects
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Scanning with SonarQube'
                bat 'sonar-scanner'  // Uncomment if SonarQube is configured
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Checking with OWASP Dependency-Check'
               bat 'dependency-check.sh --scan .'  // Uncomment for real scans
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to AWS EC2 (staging)'
                bat 'scp target/*.jar user@staging-server:/app'  // Uncomment for real deploy
            }
        }
        stage('Integration Tests') {
            steps {
                echo 'Running Selenium tests on staging'
               bat sh 'mvn verify -Pstaging-tests'  // Uncomment for real tests
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to AWS EC2 (production)'
                bat 'scp target/*.jar user@prod-server:/app'  // Uncomment for real deploy
            }
        }
    }
}
