pipeline {
    agent any

    stages {
        
        stage('Preparation') {
            steps {
                echo 'Prepartion..'
                // get the code from Git repo
                git 'https://github.com/aniayusark/mavenrepo01.git'
                
            }
        }            
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
