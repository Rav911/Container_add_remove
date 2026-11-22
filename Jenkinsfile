pipeline {
    agent any

    stages {
        stage('Create 10 Persistent Containers') {
            steps {
                sh '''
                    for i in $(seq 1 10); do
                        if [ ! "$(docker ps -aq -f name=^testinging_$i$)" ]; then
                            docker run -d --name testinging_$i alpine:latest sleep infinity
                            echo "Created container: testinging_$i"
                        else
                            echo "Container testinging_$i already exists, skipping..."
                        fi
                    done
                '''
            }
        }
    }

    post {
        success {
            echo '=== All 10 containers (testinging_1 to testinging_10) are active and preserved! ==='
        }
    }
}
