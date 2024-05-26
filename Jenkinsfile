pipeline{
    agent any
    stages {
        stage('Install Enviroment And Dependency') {
            steps {
                // Install any dependencies your Python test needs, like pip install <package>
                // sh 'pip3 --version'
                // sh 'pip3 install -r OnlineJudge_BE/deploy/requirements.txt'
                sh 'ls'
                sh 'pwd && docker build . -t oj_fe'
            }
        }
        // stage('Run Tests') {
        //     steps {
        //         // Run your Python test script
        //         // sh 'cd '
        //         // sh 'python3.8 OnlineJudge_BE/manage.py test oj'
        //     }
        // }
        stage('Start docker compose') {
            steps {
                // Run your Python test script
                sh 'ls'
                sh 'docker images'
                sh "docker-compose build"
                sh 'docker compose up -d'
            }
        }
    }
    post {
        success {
            // Actions to take if the test succeeds
            echo 'Tests passed successfully!'
        }
        failure {
            // Actions to take if the test fails
            echo 'Tests failed!'
        }
    }
}