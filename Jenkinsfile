pipeline {
    agent {
        node {
            label 'labeldockerserver'
        }
    }

    stages {
        
        stage('clean') {
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
        stage('makeupload') {
            when {
                branch 'Develone'  //only run these steps on the master branch
            }
            steps {
                sh 'docker build -t  akhil5001/akhil_repo .'
                
                
            }
        }
        stage('run') {
            when {
                branch 'Develone'  //only run these steps on the master branch
            }
            steps {
                sh 'docker container run -d --name dpone -p 80:80 akhil5001/akhil_repo:latest'
                
            }
        }
    }
}
