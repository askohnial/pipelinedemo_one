pipeline {
    agent {
        node {
            label 'labeldockerserver'
        }
    }

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t  akhil5001/akhil_repo .'
                sh 'docker push akhil5001/akhil_repo:latest'
                
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker container run -d --name dpone -p 80:80 akhil5001/akhil_repo:latest'
                
            }
        }
    }
}
