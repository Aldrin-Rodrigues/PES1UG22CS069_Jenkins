pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                checkout([$class: 'GitSCM',
                branches: [[name: '*/main']],
                userRemoteConfigs: [[url: "https://github.com/Aldrin-Rodrigues/PES1UG22CS069_Jenkins.git"]]])
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG22CS069-1'
                sh 'g++ new.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
    }

    post {
        failure {
            echo "pipeline failed"
        }
    }
}