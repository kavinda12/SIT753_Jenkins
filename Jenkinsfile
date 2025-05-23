pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building with Maven'
                // sh 'mvn clean package'  // Uncomment for real projects
            }
        }
        stage('Unit Tests') {
            steps {
                echo 'Running JUnit tests'
                // sh 'mvn test'  // Uncomment for real projects
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Scanning with SonarQube'
                // sh 'sonar-scanner'  // Uncomment if SonarQube is configured
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Checking with OWASP Dependency-Check'
                // sh 'dependency-check.sh --scan .'  // Uncomment for real scans
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to AWS EC2 (staging)'
                // sh 'scp target/*.jar user@staging-server:/app'  // Uncomment for real deploy
            }
        }
        stage('Integration Tests') {
            steps {
                echo 'Running Selenium tests on staging'
                // sh 'mvn verify -Pstaging-tests'  // Uncomment for real tests
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to AWS EC2 (production)'
                // sh 'scp target/*.jar user@prod-server:/app'  // Uncomment for real deploy
            }
        }
    }
}
