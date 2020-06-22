pipeline {
    agent {
        node {
            label 'labeldockerserver'
        }
    }

    stages {
        stage('StopRemove') {
            steps {
                sh 'ls -l'
                sh 'docker container stop dpone'
                sh 'docker container rm dpone'
                sh 'docker image rmi akhil5001/on:latest'
            }
        }
        
    }
}
