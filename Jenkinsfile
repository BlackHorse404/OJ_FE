pipeline{
    agent any
    stages {
        stage('stop all docker container & image') {
            steps {
                sh 'docker ps -aq'
                sh 'docker stop $(docker ps -aq)'
            }
        }
        stage('clean docker container & image') {
            steps {
                sh 'docker rm $(docker ps -aq)'
                sh 'docker rmi $(docker images -q)'
            }
        }
        stage('Install Dependencies and build image oj_fe') {
            steps {
                // Install any dependencies your Python test needs, like pip install <package>
                // sh 'pip3 --version'
                // sh 'pip3 install -r OnlineJudge_BE/deploy/requirements.txt'
                sh 'ls'
                sh 'pwd && docker build . -t oj_fe'
            }
        }
        stage('Start docker compose') {
            steps {
                // Run your Python test script
                sh 'ls'
                sh 'docker images'
                sh 'docker compose up -d'
            }
        }
    }
    post {
        success {
            // Actions to take if the test succeeds
            echo 'Run successfully!'
        }
        failure {
            // Actions to take if the test fails
            echo 'Run failed!'
        }
    }
}