pipeline {
    agent any

    stages {
        
        stage('Preparation') {
            steps {
                echo 'Prepartion..'
                echo 'hello world'
                // get the code from Git repo
                git credentialsId: 'ce3df5b2-3072-45aa-b9de-31aa07ae2f2d', url: 'https://github.com/aniayusark/mavenrepo01.git'
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'ce3df5b2-3072-45aa-b9de-31aa07ae2f2d', url: 'https://github.com/aniayusark/mavenrepo01.git']]])
                
            }
        }            
        stage('Build') {
            steps {
                echo 'Building..'
                withMaven(jdk: 'JDK-14', maven: 'Maven3.6.3', tempBinDir: 'D:\\Project-CICD\\temp_binary') {
    // some block
                build 'pipeline-2'     
}
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
         stage('Package') {
            steps {
                echo 'Packing..'
                sh label: '', script: 'mvn -Dmaven.test.failure.ignore clean package'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
