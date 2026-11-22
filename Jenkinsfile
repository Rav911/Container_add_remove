pipeline {
    agent any

    stages {
        stage('Auto-Create & Run Container') {
            agent {
                docker {
                    image 'alpine:latest'
                    reuseNode true
                }
            }
            steps {
                sh 'echo "=== Container Created Automatically ==="'
                sh 'cat /etc/os-release'
                sh 'sleep 5'
            }
        }
    }

    post {
        always {
            echo '=== Container Stopped & Deleted Automatically ==='
        }
    }
}
