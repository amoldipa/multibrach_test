pipeline {
    agent {label 'slave1'}
    
    stages {
        stage('Git Checkout') {
        steps {
            git branch: 'master',
                credentialsId: 'Git-https-cred',
                url: 'https://github.com/amoldipa/multibrach_test.git'
            }
        }
        stage('Build') {
            steps {
                echo "Building the code"
                sh '/usr/local/src/apache-maven/bin/mvn clean install'
            }
        }
        stage('Testing') {
            steps {
                echo 'Testing..'
                sh 'ls -la'
                sh 'sh testing.sh'                
            }
        }
        stage('Deployment') {
            steps {
                echo 'Deployment..'
            }
        }
    }
}
