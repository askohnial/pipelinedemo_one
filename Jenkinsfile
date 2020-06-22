pipeline {
    agent {
        node {
            label 'labeldockerserver'
        }
    }

    stages {
        
        stage('StopRemove') {
            when {
                branch 'Develone'  //only run these steps on the master branch
            }
            steps {
                sh 'ls -l'
                sh 'docker container stop dpone'
                sh 'docker container rm dpone'
                sh 'docker image rmi akhil5001/akhil_repo:latest'
            }
        }
        stage('Build') {
            when {
                branch 'Develone'  //only run these steps on the master branch
            }
            steps {
                sh 'docker build -t  akhil5001/akhil_repo .'
                sh 'docker push akhil5001/akhil_repo:latest'
                
            }
        }
        stage('Deploy') {
            when {
                branch 'Develone'  //only run these steps on the master branch
            }
            steps {
                sh 'docker container run -d --name dpone -p 80:80 akhil5001/akhil_repo:latest'
                
            }
        }
    }
}
